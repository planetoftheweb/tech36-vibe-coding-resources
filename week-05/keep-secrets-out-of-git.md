# Keeping Secrets Out of Git

Your app probably uses API keys: for an AI model, payments, email, or a database. A key is like a password for your account. If it ends up in your git history, anyone who can see your repo can use it, and you pay the bill. This lesson comes from a real security pass on course projects. It walks through how to keep keys out, how to check, and what to do if one slips.

You'll need a project in git and a coding harness (Claude Code, Cursor, or Codex). No harness? You can still read along and paste the prompt at the end into any AI with your code.

## 1. Why committed keys are dangerous

- **Public repos are scanned constantly.** Bots watch GitHub for new commits and pull out anything that looks like a key, often within minutes. People have woken up to huge cloud bills from a key that was public for one afternoon.
- **Git never forgets.** Deleting the key in a later commit doesn't remove it. It's still in the history, and anyone can scroll back to find it.
- **Private repos aren't a vault.** Repos get made public later, shared with collaborators, or cloned onto laptops that get lost. Treat every repo as if it might go public someday.

The fix is simple: keep keys in a `.env` file on your computer, and never let git track that file.

## 2. Ignore your env files

Add these lines to `.gitignore` in the root of your project:

```gitignore
# Secrets
.env*
!.env.example
```

- `.env*` ignores `.env`, `.env.local`, `.env.production` and any other env file.
- `!.env.example` makes one exception. `.env.example` lists the names of your keys with fake values, so others know what to set up:

```bash
# .env.example (safe to commit, no real values)
AI_API_KEY=your-key-here
PAYMENT_SECRET_KEY=your-key-here
```

Check that it works with `git check-ignore`:

```bash
git check-ignore -v .env .env.local .env.example
```

It prints the rule that ignores each file. If `.env` shows up, it's ignored. If `.env.example` doesn't show up, it will be committed, which is what you want.

## 3. Is an env file already tracked?

Here's the trap: **an ignore rule doesn't untrack a file git already knows about.** If you committed `.env` before adding the rule, git keeps tracking it. Check:

```bash
git ls-files | grep -i env
```

If you see anything except `.env.example`, stop tracking it:

```bash
git rm --cached .env
git commit -m "Stop tracking .env"
```

`--cached` removes the file from git only. **The file stays on your disk**, so your app keeps working. But the old commits still contain it, so if the file had real keys, go to step 6 and rotate them.

## 4. Scan your history with gitleaks

[gitleaks](https://github.com/gitleaks/gitleaks) searches every commit for things that look like secrets. Install it (for example `brew install gitleaks` on a Mac), then run this in your project:

```bash
gitleaks detect --redact
```

`--redact` hides the actual values in the output, so you don't leak them again in your terminal or a screenshot. It lists the file, commit and type of each finding.

No gitleaks? Check one file by name. This lists every commit that ever touched it, even if you deleted it later:

```bash
git log --all --oneline -- .env
```

Not every finding is a real problem. Some values are **public by design**: they're meant to ship in your website's code, where anyone can see them.

| Usually public, OK to commit | Real secret, never commit |
| --- | --- |
| Firebase web config (`apiKey`, `projectId` and friends in your front end) | Firebase service account JSON files or admin keys |
| Stripe publishable keys (start with `pk_`) | Stripe secret keys (start with `sk_`) and webhook secrets (`whsec_`) |
| Stripe price IDs (start with `price_`) | AI model API keys (OpenAI, Anthropic, Gemini and others) |
| Analytics or map IDs restricted to your domain | Database passwords and connection strings |

One more trap: env names that start with `VITE_` or `NEXT_PUBLIC_` are copied into your website's code, so never put a real secret in one.

Public values are protected by other rules, like Firebase security rules or restricting a key to your domain. If you're not sure about a finding, treat it as secret.

## 5. Block secrets before they're committed

A pre-commit hook runs a check every time you commit and stops the commit if it finds a secret. Pick one option.

**Option A: a plain git hook.** Create `.git/hooks/pre-commit`:

```bash
#!/bin/sh
gitleaks protect --staged --redact
```

Then make it runnable:

```bash
chmod +x .git/hooks/pre-commit
```

This only lives on your computer. It isn't shared with anyone who clones the repo.

**Option B: husky (for JavaScript projects).** husky stores hooks in your repo so everyone gets them:

```bash
npm install --save-dev husky
npx husky init
echo "gitleaks protect --staged --redact" > .husky/pre-commit
```

Test it: put a fake key in a file (ask your AI for a made-up test value that looks like a real key), stage it, and try to commit. The hook should block it. Then delete the fake key.

## 6. If a key leaks: rotate it first

1. **Rotate the key right away.** Go to the service's dashboard, create a new key, update your `.env` and your hosting settings, then delete or disable the old key. This is the only step that actually stops someone from using it.
2. **Then clean up git.** Remove the key from your code and add the ignore rule from step 2. To scrub it out of old commits, tools like `git filter-repo` can rewrite history, but it's tricky and changes everyone's copy of the repo, so ask for help. It also **doesn't un-leak a key.** Bots, forks and clones may already have it. That's why you rotate first.
3. **Then check for damage.** Look at the service's usage and billing pages for activity you don't recognize.

Using Google Cloud or Firebase? Also restrict each API key to your site and the APIs it needs, turn off APIs you don't use, and set a budget alert in Billing. Set usage alerts or spending caps in your other paid services too. The [Week 4 security test](../week-04/security-test-step.md#lessons-from-a-real-key-leak) explains why.

## Checklist

|  |  |
| --- | --- |
| ☐ | Keys live in `.env`, never in your code |
| ☐ | `.gitignore` has `.env*` and `!.env.example` |
| ☐ | `git check-ignore -v .env` confirms it's ignored |
| ☐ | `git ls-files` shows no env file except `.env.example` |
| ☐ | `gitleaks detect --redact` is clean, or every finding is public by design |
| ☐ | A pre-commit hook runs `gitleaks protect --staged --redact` |
| ☐ | You know where to rotate each key if it leaks |

## Prompt for your AI coding tool

Paste this into Claude Code, Cursor, or Codex inside your project:

```text
Do a secrets check on this project. Don't print any secret values, and don't change git history.

1. Make sure .gitignore includes ".env*" and "!.env.example". Confirm with git check-ignore.
2. Run "git ls-files" and tell me if any env file other than .env.example is tracked. If so, untrack it with "git rm --cached" (keep the file on disk) and tell me which keys it held so I can rotate them.
3. Create or update .env.example with every key name the code uses and placeholder values only.
4. If gitleaks is installed, run "gitleaks detect --redact". For each finding, tell me if it's a real secret or public by design (like Firebase web config, Stripe publishable keys or price IDs), and why.
5. Search the code for hard-coded keys and move any real secrets into .env.
6. Set up a pre-commit hook that runs "gitleaks protect --staged --redact".
7. Give me a short list of any keys I should rotate and where to do it. Show me your changes before you commit.
```

> **Never paste real keys into an AI chat.** The prompt above asks your tool to work with key names, not values.

---

[Back to Week 5](README.md) · [Main index](../README.md)
