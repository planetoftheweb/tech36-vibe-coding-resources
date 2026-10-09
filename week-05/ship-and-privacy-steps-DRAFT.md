> **DRAFT: pending approval from the instructor (Ray Villalobos).** This is a proposed addition to Assignment 5 (the optional stretch). It is not part of the official assignment yet and may change or be removed. Until it is approved, follow the steps in [README.md](README.md).

# Proposed Steps: Ship Pages and Repo Files, then a Privacy Check (Assignment 5)

## Where they would go

As two new steps right after "4. Publish It and Add It to VibeIt":

1. Pick Your Project (unchanged)
2. Core Track: Finish and Polish (unchanged)
3. Advanced Track (optional). Running steps 5 and 6 in a coding harness would count as your pro-tool step.
4. Publish It and Add It to VibeIt (unchanged)
5. **Ship Pages and Repo Files** (new)
6. **Privacy Check with Your Coding Harness** (new)
7. Write Your "What I Did to Finish It" Outline (was 5)
8. Reflect (was 6)

A5 stays optional and is not required for the Certificate.

## 5. Ship Pages and Repo Files

Real sites have the boring pages people look for before they trust you: a privacy policy, terms, an about page, a way to reach you, and a footer that links them all. Real repos have a README, a license, and files that keep your keys safe. Your coding harness can build them in one go.

1. Open your project in your coding harness (Claude Code, Cursor, or Codex) and paste the harness version of the [Ship Files Prompt](ship-files-prompt-DRAFT.md). No harness? Paste the fallback version into any AI and give it your live site link.
2. Answer its questions one at a time. It figures out what it can from your code and only asks when it's unsure.
3. Check its plan before it builds. Building everything can use a lot of credits, so skip the extras if you want.
4. Review the changes before it commits, then fill in every [bracket] it lists for you.
5. Publish again and click every footer link on your phone and your computer.

> **These are drafts, not legal advice.** The privacy policy and terms should describe only what your site really does. Never put a real key in .env.example or your README.

## 6. Privacy Check with Your Coding Harness

Now check that your new pages tell the truth. A real app earns trust by being clear about what it collects, where that information goes, and how people can take it back.

1. In the same project, paste the harness version of the [Privacy Test Prompt](privacy-test-prompt-DRAFT.md). No harness? Paste the main version into any AI and give it your live site link.
2. Answer its questions.
3. Review what it found and copy the full results. You'll paste them into your submission. It checks that your privacy policy, terms, and about page match what your code really does.
4. Pick at least 2 problems to fix, or fix them all. Fix them however you like. The prompt can also fix them for you, but that can use a lot of credits.
5. Publish again, then send this in the same chat and copy what it says:

```text
I made the fixes. Run the privacy check again and tell me what got better and what still needs work.
```

> **Educational, not legal advice.** This check teaches the basics of privacy laws like GDPR and CCPA. It can't tell you your app is legally compliant. Use made-up details when testing and never your real password.

## What would change in "How to submit"

Three new items would be added to the list:

4. Your ship pages and repo files (links to your new pages, plus your repo link if you have one)
5. Your privacy test results
6. The 2 or more problems you fixed and what the retest showed

## New checklist rows

|  |  |
| --- | --- |
| ☐ | Ship your pages (privacy, terms, about, contact, 404, footer) and repo files (README, .gitignore, .env.example, LICENSE), and fill in every [bracket] |
| ☐ | Run the privacy check and confirm your pages match your code |
| ☐ | Fix at least 2 problems, publish again, and run the retest |
| ☐ | **Submit:** your VibeIt app link, finish outline, reflection, ship pages and repo files, privacy test results, and your fixes plus retest |

---

[Back to Week 5](README.md) · [Main index](../README.md)
