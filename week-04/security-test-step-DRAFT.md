> **DRAFT: pending approval from the instructor (Ray Villalobos).** This is a proposed addition to Assignment 4. It is not part of the official assignment yet and may change or be removed. Until it is approved, follow the steps in [README.md](README.md).

# Proposed Step: Security Test Your Live Site (Assignment 4)

## Where it would go

As a new **step 6**, right after "5. Publish It and Add It to VibeIt." The build outline would become step 7 and the reflection step 8.

## 6. Security Test Your Live Site

Your site works. Now make sure a stranger can't read data that isn't theirs, change it, or use your keys. An AI can check the common mistakes in a few minutes.

1. Paste the [Security Test Prompt](security-test-prompt-DRAFT.md) into an AI. One that can open websites works best (Claude in Chrome or ChatGPT agent mode). If yours can't, the prompt tells you what to give it instead.
2. Answer its questions, starting with your live site link. If you have a GitHub repo or can copy your code, share that too.
3. Review what it found and copy the full results. You'll paste them into your submission.
4. Pick at least 2 problems to fix, or fix them all. Fix them however you like. The prompt can also write an optional fix prompt for your AI agent, but that can use a lot of credits.
5. Publish again, then send this in the same chat and copy what it says:

```text
I made the fixes. Run the security check on my site again and tell me what got better and what still needs work.
```

> **Test only your own site.** Give it your published URL. Use made-up test accounts, never your real password, and never paste a secret key into the chat. If the test finds an exposed key, make a new key in that service and delete the old one.

> **Built a game with no login or database?** Run the test anyway. It still checks for exposed API keys, HTTPS, and leftover debug info. If it only finds 1 problem, fix that one and say so in your submission.

## What would change in "How to submit"

Two new items would be added to the list:

4. Your security test results
5. The 2 or more problems you fixed and what the retest showed

## New checklist rows

|  |  |
| --- | --- |
| ☐ | Run the security test on your live site |
| ☐ | Fix at least 2 problems, publish again, and run the retest |
| ☐ | **Submit:** your VibeIt app link, build outline, reflection, security test results, and your fixes plus retest |

---

[Back to Week 4](README.md) · [Main index](../README.md)
