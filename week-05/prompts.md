# Week 5 Prompts: Optional Stretch: Ship Checklist

Every suggested prompt from Assignment 5, in one place. They're suggestions. Rewrite them, combine them, or skip them. Replace anything in [square brackets] with your own details.

## 2. Core Track: Finish and Polish

```text
Look at my project like a first-time visitor who has never seen it. List the five things that make it feel unfinished or confusing, then help me fix them one at a time.
```

## 5. Write Your "What I Did to Finish It" Outline

```text
Review our conversation and create a short outline of what we changed to finish this project. No more than 10 bullet points, each under 150 characters. Focus on what was polished, fixed, or added.
```

## Investigate, Build, Check

Four prompts, one per step. Use a different AI tool or model for the Check step than the one that did the Build step. See [Investigate, build, check](investigate-build-check.md) for why.

### 1. Investigate (write the done list before touching code)

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

### 2. Build (against the done list only)

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

### 3. Check (second AI or different model, on the live URL)

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

### 4. Loop back (fix until the check passes)

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

[Back to Week 5](README.md) · [Main index](../README.md)
