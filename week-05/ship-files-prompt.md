# TECH 36 Ship Pages and Repo Files Prompt

> **Also available as a skill:** install the [ship-files skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/ship-files) in Claude Code or Claude.ai, or use it in a ChatGPT Project.

**Main version: run it in a coding harness** (Claude Code, Cursor, or Codex) with your project open. It reads your code and planning files, asks only what it can't figure out, then builds the pages and files. No harness? Use the **short fallback** at the bottom in any AI.

The policy pages it writes are drafts to help you learn, not legal advice.

## Main version (coding harness)

```
Help me get this project ready to ship with the pages and repo files a real site needs. I'm a beginner, so use plain words and explain any tech or legal term the first time you use it.

Don't create, edit, or delete any files until I've approved your plan.

Step 1. Read the repo yourself before asking me anything:
- Planning files: PRD, agents.md, CLAUDE.md, and DESIGN.md, for who it's for, what it does, who made it, and the look.
- The code, config, and package.json: what personal information it collects, which services and AI APIs it uses, and how to run it.
- How keys are used: .env files and any key written straight into the code. Search git history for committed keys, tokens, and .env files.
- Deploy config and the live URL.
- Which of the pages and files below already exist.

Step 2. Ask me only what you can't see, one question at a time, and wait for each answer. Aim for 0 to 3 questions. Tell me any guess in one sentence so I can confirm it. Usually that's:
- Public contact: an email I'm OK making public, or a simple contact or feedback form. Remind me not to post a personal phone number or home address.
- License, explained in one plain sentence each: MIT (anyone can use and change it, as long as they keep my name on it; the default), Apache 2.0 (like MIT, plus extra patent protection), GPL (anyone can use it, but if they share a changed version they must share their code too), or no license (people can look but not reuse it). Default to MIT if I'm not sure.
- Where my users live (US only, or anywhere including Europe) and whether kids under 13 might use it, if the planning files don't say.
- Whether the live site differs from this repo, only if something looks out of sync.

Step 3. Show me a short plan: each page and file you'll create or update, one line each, and wait for my OK. Warn me that building all of this can use a lot of credits, so I can pick fewer items.

Step 4. Once I say OK, build only these.

Site pages:
- Privacy policy: what the site collects, why, where it's stored, which outside services get it (including AI APIs), how long it's kept, and how users can see, export, or delete their data. Add the GDPR or CCPA basics only if they fit where my users live, and a line about kids if kids might use it.
- Terms of use: what the site is for, what users shouldn't do, that it's provided as is, and how to contact me.
- About: who made it, who it's for, and what it does, in a friendly voice.
- Contact or feedback: the email or form I chose.
- A friendly 404 page: a short, kind message and a button back to the home page.
- A footer on every page linking to all of the pages above.

Repo files:
- README.md: what the project is, the live link, the tools it uses, and simple steps to run it.
- .gitignore: make sure .env files, keys, and other secrets are ignored. If a secret is already committed, show me only the first 4 characters, tell me which service it's for, and tell me to make a new key and delete the old one. Don't rewrite git history or force push without asking me first.
- .env.example: the key names the app needs, with empty or placeholder values. Never real values.
- LICENSE: the license I picked, with my name and the current year.
- SECURITY.md (optional, ask me): one short paragraph on how to report a security problem using my public contact.

Nice extras (ask me before adding each one): a favicon, a social share image, and a clear page title and one-sentence meta description on each page.

Rules for the policy pages: describe only what the site really does, based on the code and my answers. Never invent features, services, or promises. Use [brackets] for anything I need to fill in. Put this at the top of the privacy policy and terms: "Draft. Not legal advice. Review before relying on it."

Rules for everything: change nothing else, add no new features, and don't redesign anything. Match DESIGN.md and the site's existing fonts, colors, and style. Check the new pages and footer on both phone and desktop.

Step 5. Show me the diff, file by file, with one plain sentence per change, and wait for my OK before you commit. Then commit with a clear message. Finish with a list of every [bracket] I still need to fill in and how to test the new pages on the live site.
```

## Short fallback (any AI, no harness)

```
Help me add the pages a real website needs. Use plain words.

I'm sharing: my live link, plus my code or GitHub repo if I have it. If I have them, I'm also sharing my PRD, agents.md, CLAUDE.md, or DESIGN.md.

Read what I share first. Then ask me only what you still need, one question at a time. Usually that's: what personal information the site collects and which services it uses (if you can't tell), my public contact (an email I'm OK sharing, or a form, never a personal phone or address), where my users live, whether kids under 13 might use it, and which license I want (explain MIT, Apache 2.0, GPL, and no license in one sentence each; default to MIT).

Then write each of these in its own code block, with a note saying where it goes: a privacy policy, terms of use, about, contact or feedback, a friendly 404 page, and a footer linking them all. If I have a repo, also write README.md, .gitignore (keeps .env files and keys out), .env.example (key names only), and LICENSE.

Policy pages must describe only what the site really does, use [brackets] for anything I need to fill in, and start with "Draft. Not legal advice. Review before relying on it."

Optional: last, write one prompt I can paste into Lovable or my coding AI to add the pages and footer. Start it with a warning that it can use a lot of credits. It must add only these pages, change nothing else, match my site's style, and check phone and desktop. Finish with a list of every [bracket] I still need to fill in.
```

## Check your work

After the pages are live, run the [Privacy Test Prompt](privacy-test-prompt.md) (step 6 of Assignment 5). It checks that your new pages match what your code really does.

---

[Back to Week 5](README.md) · [Main index](../README.md)
