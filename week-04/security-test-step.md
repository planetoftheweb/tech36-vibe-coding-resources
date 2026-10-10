# Assignment 4 Step: Security Test Your Live Site

This step goes right after "5. Publish It and Add It to VibeIt" in [Assignment 4](README.md). The build outline becomes step 7 and the reflection step 8. If the course site lists different submission boxes, follow the course site.

Prefer a skill? Use the [security-check skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/security-check) in Claude Code, Claude.ai, or a ChatGPT Project.

## 6. Security Test Your Live Site

Your site works. Now make sure a stranger can't read data that isn't theirs, change it, or use your keys. An AI can check the common mistakes in a few minutes.

1. Open your project in a coding harness (Claude Code, Cursor, or Codex) and paste the main version of the [Security Test Prompt](security-test-prompt.md). It reads your code and database rules itself.
2. Answer its questions. Because it reads your code first, there should only be a few.

   > **New to harnesses?** We cover them in Week 5. For now: connect your project to GitHub (the GitHub button in Lovable, or save to GitHub in AI Studio), then open it in Cursor with File > Open Folder, or clone it in a terminal and type `claude`. If that's too much this week, paste the short fallback at the bottom of the prompt into any AI with your live link and your code or screenshots.
3. Review what it found and copy the full results. You'll paste them into your submission.
4. Pick at least 2 problems to fix, or fix them all. Fix them however you like. The prompt can also write an optional fix prompt for your AI agent, but that can use a lot of credits.
5. Publish again, then send this in the same chat and copy what it says:

```text
I made the fixes. Run the security check on my site again and tell me what got better and what still needs work.
```

> **Test only your own site.** Give it your published URL. Use made-up test accounts, never your real password, and never paste a secret key into the chat. If the test finds an exposed key, make a new key in that service and delete the old one.

> **Built a game with no login or database?** Run the test anyway. It still checks for exposed API keys, HTTPS, and leftover debug info. If it only finds 1 problem, fix that one and say so in your submission.

## What to submit

1. Your VibeIt **app** link (publish your game or site to VibeIt, then submit that link, not a profile ID)
2. Your build outline
3. Your reflection (about 500 characters), naming which principles you applied
4. Paste your security test results
5. Your fixes and retest (the 2 or more problems you fixed and what the retest showed)

## Checklist rows

|  |  |
| --- | --- |
| ☐ | Run the security test in a coding harness (or the short fallback in any AI) |
| ☐ | Fix at least 2 problems, publish again, and run the retest |
| ☐ | **Submit:** your VibeIt app link, build outline, reflection, security test results, and your fixes and retest |

---

[Back to Week 4](README.md) · [Main index](../README.md)
