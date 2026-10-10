# TECH 36 Privacy and Data Test Prompt

> **Also available as a skill:** install the [privacy-check skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/privacy-check) in Claude Code or Claude.ai, or use it in a ChatGPT Project.

**Main version: run it in a coding harness** (Claude Code, Cursor, or Codex) with your project open. It reads your code itself, so it only asks a question or two. No harness? Use the **short fallback** at the bottom in any AI.

These are educational checks to help you build good habits. They are not legal advice.

## Main version (coding harness)

```
Run a beginner-friendly privacy and data check on this project. I'm a beginner, so use plain words and explain any tech or legal term the first time you use it. These are educational checks, not legal advice. Say that once at the top of your reply, and never call anything "compliant" or "legal."

Don't change any files, run database changes, or delete data until I pick what to fix. If you find personal information or a secret key in the code, show only the first 4 characters.

Step 1. Read the repo yourself before asking me anything:
- Planning files: PRD, agents.md, CLAUDE.md, and DESIGN.md, to learn who the app is for and what it's meant to collect.
- The code, config, and package.json: every form, database table, login setup, browser storage, cookie, analytics script, and log that touches personal information.
- Every outside service that receives that data (database, login, analytics, AI APIs, email, payments) and what gets sent to each one.
- The privacy policy, terms, About, and Contact pages, and the footer that links them.
- Deploy config and the live URL.

Step 2. Ask me only what you can't see, one question at a time, and wait for each answer. Aim for 0 to 3 questions. Tell me any guess in one sentence so I can confirm it. Usually that's: where my users live (US only, or anywhere including Europe), whether kids under 13 might use it, and whether the live site differs from this repo.

Step 3. Check these, and tell me which file you looked at for each one:
- Privacy policy and terms: do they exist, are they linked in the footer and near sign-up, and does every claim match what the code really does? List any mismatch, like a service the policy leaves out or a promise the app doesn't keep. Flag template text and any [brackets] still to fill in.
- Consent: does the app say what it collects and why before collecting it? Do cookies, analytics, or trackers load before anyone agrees?
- Collect only what you need: list each piece of personal information. Does the app actually use it? Flag anything extra.
- User control: can users see, export, fix, and delete their account and data? When something is deleted, is it really gone?
- Where the data goes: which service stores it, in which region if the config says, and which outside companies process it, like an AI API that gets what people type. Does the site tell users?
- GDPR and CCPA basics, in plain words: GDPR is Europe's privacy law and CCPA is California's. Based on where my users live, list the 3 to 5 basics that matter most.
- Kids: if kids under 13 might use it, explain that collecting their information has extra rules in the US (COPPA).

Rate how serious each problem is:
- High: personal information is collected or shared without people knowing, or they can't get it deleted.
- Medium: something users would expect is missing or unclear.
- Low: good practice. Fix it when you can.

Reply in this format:
Note: one line saying these are educational checks, not legal advice.
What works: 2 or 3 things, one sentence each.
What to fix: up to 5 problems, numbered, worst first. For each one: a short title, the rating (High, Medium, or Low), the file it's in, what you found, and why it matters to a real user.
How to improve it: 3 suggestions, most important first. Each is one short sentence (under 20 words) that starts with an action word like Add, Remove, Move, Rewrite, Ask, or Explain. For new wording, put the new words in quotes after a colon.
Example: Add a line above the Sign up button: "By signing up, you agree to our Privacy Policy and Terms."

Then ask me which problems I want to fix (at least 2, or all of them) and wait. Before you start, warn me that fixing can use a lot of credits, so I can fix things myself instead. Fix only what I pick, change nothing else, add no new features, and don't delete real user data. If you write or change a privacy policy or terms, describe only what the app really does, use [brackets] for anything I need to fill in, and mark it "Draft. Not legal advice. Review before relying on it." Show me the diff before you commit and wait for my OK. Check phone and desktop.
```

## Short fallback (any AI, no harness)

```
Run a beginner-friendly privacy check on my website. Use plain words. These are educational checks, not legal advice, so never call anything "compliant." Only look at my site and what I share. Use made-up details for any form, and never ask for my real password.

I'm sharing: my live link, plus my code or GitHub repo if I have it (or screenshots of every page, including the footer, sign-up, and account page). If I have them, I'm also sharing my PRD, agents.md, CLAUDE.md, or DESIGN.md.

Read what I share first. Then ask me only what you still need, one question at a time. Usually that's where my users live and whether kids under 13 might use it.

Check: a privacy policy and terms that match what the site really does, consent before collecting data or loading cookies and analytics, collecting only what the app needs, a way to see, export, or delete your data, where the data goes (including AI APIs), and the GDPR and CCPA basics in plain words. Rate each problem High, Medium, or Low.

Reply with: a one-line "not legal advice" note, What works (2 or 3 things), What to fix (up to 5, numbered, worst first), and How to improve it (3 short action sentences).

Then ask which problems I want to fix (at least 2, or all of them). Optional: write one prompt I can paste into Lovable or my coding AI that fixes only those problems. Start it with a warning that it can use a lot of credits. Any policy text must describe only what the site does, use [brackets] to fill in, and be marked as a draft, not legal advice.
```

## Retest

After you make your fixes and publish again, send this in the same chat:

```
I made the fixes. Run the privacy check again and tell me what got better and what still needs work.
```

---

[Back to Week 5](README.md) · [Main index](../README.md)
