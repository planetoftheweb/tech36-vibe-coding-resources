# Week 1: Introduction to Vibe Coding

**Assignment 1: Vibe Code a Dashboard**

## This week in plain words

Vibe coding means building software by describing what you want in plain language and letting an AI write the code. You look at the result, say what to change, and run it again. The skill is in the asking and the steering, not in typing code. You don't have to become a programmer, but along the way you'll pick up real ideas like hosting, logins, databases and debugging.

This week you'll use a chatbot to turn a spreadsheet (a CSV file) into an interactive dashboard, then keep improving it.

## Key ideas

- **The vibe coding spectrum.** Tools range from beginner to pro.
  - *Chatbots* (Claude, ChatGPT, Gemini) build single pages with no setup or accounts.
  - *No-code platforms* (Lovable, Replit, v0) build full apps with databases, logins and payments.
  - *Developer tools* (Cursor, VS Code, Claude Code, Codex) let you see every file and pick your own stack.
- **AI output changes every time.** The same prompt can give different results. That's normal. Regenerate, refine, and be more specific when you want more consistent results.
- **Artifacts and Canvas.** Claude Artifacts, ChatGPT Canvas and Gemini Canvas open a side panel where the AI builds a small app you can preview, edit, download and share.
- **Each follow-up edits what you already have.** Be specific: name the chart, the metric or the part of the layout you want changed. Think about the controls your reader needs, like dropdowns, search boxes, date ranges and toggles.
- **Linked charts.** Ask for charts that talk to each other, so clicking one filters the others.
- **Steer the look.** Paste a screenshot, a few color codes, or say "match the style of a modern admin panel." Sites like Dribbble and Behance are good places to find references.
- **Ask for libraries by name.** Chart.js is simple, D3.js handles complex visuals, Plotly does scientific and 3D charts.
- **Small upgrades that feel professional.** Light and dark mode that follows your system setting, settings remembered between visits (local storage), and drag-and-drop file uploads that turn a one-time dashboard into a reusable tool.
- **Put AI inside your app.** You can ask for an assistant panel that answers questions about your data using an AI model's API.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | Every suggested prompt for this week in one place, ready to copy |
| [../week-02/agents-md-build-rules.md](../week-02/agents-md-build-rules.md) | Optional: a rules file you can paste into a chatbot so it builds the way you want |

---

## Assignment 1: Vibe Code a Dashboard

**Tool:** Default path is [Claude Artifacts](https://claude.ai). Prefer [Google Gemini](https://gemini.google.com) or [ChatGPT Canvas](https://chatgpt.com)? Fine: use whichever you're comfortable with. Whichever you pick, you need a public share link at the end.

Find a CSV dataset, upload it to Claude, build an interactive dashboard, iterate on it, and share the result.

> **The point of this assignment:** get comfortable directing an AI and iterating. The win is not the first thing the AI hands you. It's what you do next: change the charts, add controls your reader needs, fix what's wrong, and push past the first draft. If your dashboard looks the same as the AI's first attempt, you haven't done the assignment yet.

> **How to submit:** In your submission for this assignment, include all three:
>
> 1. Your VibeIt **app** link (publish your project to VibeIt, then submit the link to the app itself, not a profile ID)
> 2. Your build outline
> 3. Your reflection (about 500 characters)

> **Week 1 live habit: test before you submit.** Publish → open the live URL in a private/incognito window → submit the VibeIt **app** link (the entry that opens your project, not a profile ID). If it doesn’t load in a private window, it won’t load for me. A broken link is the most common reason work doesn’t count.

> **One project or four, your call.** You can treat the course as one project you grow week to week, or build a separate project for each assignment. Both are completely fine. Do whatever keeps you motivated.

> **Checkpoint before you build: Vibe Glossary.** Before you dive into the dashboard, open the [Vibe Glossary](https://vibeglossary.com) and do **Learn Mode on Overlays** (Modal / Popover / Tooltip) **or** reach **Tinkerer (200 pts)**. Keep the link that proves you finished it handy. Use the Glossary as your plain-language reference all term: components, APIs, auth, and more, with live examples and quick quizzes.

---

### 1. Find a Dataset

Pick a CSV that interests you. It doesn't need to be large. Even a few dozen rows works fine as long as there's enough variety to make interesting charts. Some places to look:

[data.gov](https://data.gov) · [Kaggle](https://www.kaggle.com/datasets) · [Google Dataset Search](https://datasetsearch.research.google.com) · [World Bank](https://data.worldbank.org) · [FiveThirtyEight](https://github.com/fivethirtyeight/data) · or export something from an app you already use.

---

### 2. Build Your Dashboard

Upload your CSV to [Claude](https://claude.ai) (or Gemini / ChatGPT if that's your path) and start building. Iterate at least 2-3 times. Push it past the first draft.

> **All prompts below are suggestions.** Rewrite them, combine them, ignore them, or go in a completely different direction. The best dashboards come from your own ideas about what your data needs. And remember: the AI is a conversation. If you don't know what chart type to use, or you want to brainstorm ideas, just ask. "What D3 chart types would work well with this data?" is a perfectly good prompt.

**Suggested prompts to get you started:**

```text
Describe this dataset. What columns does it have? How many rows? Are there quality issues like missing values or duplicates?
```

```text
Build an interactive HTML dashboard from this data with summary cards, at least 3 chart types, a searchable data table, and a category filter. Make it look like a polished admin panel, not a generic default style.
```

**Ideas for follow-up iterations (pick what fits your data):**

```text
Add a light/dark mode toggle. Use CSS variables. Default to system preference. Remember the setting between reloads.
```

```text
Add cross-chart interactivity. Clicking a category in one chart filters the others.
```

```text
Add an AI assistant panel to the sidebar that answers questions about the current dataset. Use the Claude API (or another model's API).
```

Don't limit yourself to these. Talk to the AI. Ask it for ideas, ask it to critique its own work, ask it how to fix something. The conversation is the tool.

---

### 3. Share It and Add It to VibeIt

In Claude, use **Publish** / **Share** on the Artifact to generate a public link. In Gemini Canvas or ChatGPT Canvas, use that tool's share or publish option instead. Copy the link and test it in a private window. Shared dashboards are public, so don't include personal or sensitive data.

Then add your project to [VibeIt](https://vibeit.work), your catalog of everything you build in this course. Paste your share link and let VibeIt fill in the details. **You choose whether each entry is public or private.** The link you submit for this assignment is your **VibeIt app link**: the one that opens your project for a stranger, not a profile ID.

---

### 4. Generate a Build Outline

Paste this into the same conversation where you built your dashboard:

```text
Review our conversation and create a short outline of what we built together. No more than 10 bullet points, each under 150 characters. Focus on what was built or changed, not the prompts I typed.
```

---

### 5. Write a Short Reflection

500 characters or less. Name one thing you pushed past the first draft on: what did you change between iterations, and why? Keep it casual.

---

### Completion

No grades. Soft deadlines. The **Certificate** is based on attending the sessions plus **A1–A4 submitted and up to date**. (A5 is an optional stretch later, not required for the Certificate.)

---

## Sources

- Assignment 1 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, Part 1: Introduction to Vibe Coding.
- Gist: [An AGENTS.md file for chatbots to use when building apps](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0), referenced as an optional extra.

[Back to the main index](../README.md)
