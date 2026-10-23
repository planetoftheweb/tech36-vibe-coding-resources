# Investigate, Build, Check

This week's professional workflow in four words: **investigate, build, check**, then loop.

A recent paper, [*From Evidence to Action: How Tool-Using Agents Fail*](https://huggingface.co/papers/2610.07753), studied AI agents that use tools. On a paper checklist, strong setups often picked the right next action about **95%** of the time. In live runs, they succeeded only about **52%** of the time. A common failure: they changed things before they had finished looking.

That's easy to avoid with a habit.

## The habit

1. **Investigate first.** Have the AI read your project and write down what "done" means *before* it changes anything.
2. **Build against that list.** Only then make changes, one clear item at a time.
3. **Check with a second AI tool or model** (different from the one that built). Point it at the **live** site. Ask it to try a real sign-in, the key flow, confirm the live URL works, and run a **stranger test** (a brand-new account must not see someone else's data).
4. **Loop fixes back** until the check passes. Don't ship on "the builder said it was fine."

## Why this matters

Two real examples, with names left out:

- An AI model's own tests all passed. A brand-new account could still open another clinic's patient records.
- An AI-shipped app update went out missing its config. A user got zero credits.

Passing tests inside the chat is not the same as a stranger using the live URL.

> **The stranger test is a must for anything with accounts or data.** Make a new account. Can it see someone else's stuff? If yes, you're not done, even if the builder AI sounds cheerful.

## How this fits Assignment 5

If you take the optional stretch, use this pattern when you polish, [ship your pages, and run the privacy check](ship-and-privacy-steps.md). The prompts below are copy-paste starters. Swap in your live URL and project details.

Use a **different** AI tool or model for the Check step than the one that did the Build step.

## 1. Investigate (write the done list before touching code)

```text
You are helping me finish a live web project. Do not change any code yet.

1. Read the project (files, README, and any planning notes I share).
2. Open or review the live URL I give you: [PASTE LIVE URL]
3. Write a short "done list" of what finished means for THIS project. Include:
   - First impression (title, one-line description, first minute)
   - Main user flow that must work end to end
   - Trust details (links, about, privacy/terms if they apply)
   - Auth and data rules (who can see what)
   - A stranger test: a brand-new account must not see another user's data
4. Mark each item: already true / unclear / missing.
5. Stop. Wait for my OK before building anything.
```

## 2. Build (against the done list only)

```text
Here is the done list we agreed on:

[PASTE DONE LIST]

Build against that list only. For each change:

1. Name which done-list item you are working on.
2. Make the smallest change that moves that item to "done."
3. Tell me what to click on the live site to verify it.
4. Do not expand scope. If you notice something new, add it to a "later" list instead of building it now.

Live URL: [PASTE LIVE URL]
```

## 3. Check (second AI or different model, on the live URL)

```text
You are a checker, not the builder. Do not rewrite the app. Test the LIVE site.

Live URL: [PASTE LIVE URL]

Done list we claimed to finish:

[PASTE DONE LIST]

Please check and report PASS / FAIL / BLOCKED for each:

1. The live URL loads in a private/incognito window (no special login of mine).
2. Real sign-in (or guest path) works for a normal user.
3. The key flow works start to finish (describe what you tried).
4. Stranger test: create or use a brand-new account. Confirm it cannot see another user's or another org's data.
5. Anything on the done list that still looks unfinished.

Rules:
- Prefer the live site over reading code.
- If you cannot complete a step, say BLOCKED and what you needed.
- End with: ship / fix then recheck / do not ship, and the top 3 fixes.
```

## 4. Loop back (fix until the check passes)

```text
The checker reported these failures:

[PASTE CHECKER REPORT]

For each FAIL:

1. Restate the done-list item it maps to.
2. Propose the smallest fix.
3. After I approve, make the fix.
4. Give me a short retest script for the live URL (including the stranger test if data/auth was involved).

When you think we are done, I will run the Check prompt again with a different AI tool or model. Do not declare "shipped" yourself.
```

## Checklist

|  |  |
| --- | --- |
| ☐ | The AI wrote a done list before changing anything |
| ☐ | Every change maps to an item on the done list |
| ☐ | A second AI tool or model checked the live URL |
| ☐ | The stranger test passed (a new account can't see anyone else's data) |
| ☐ | Fixes looped back until the check passed |

---

[Back to Week 5](README.md) · [Main index](../README.md)
