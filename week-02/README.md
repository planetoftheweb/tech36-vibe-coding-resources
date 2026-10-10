# Week 2: From Dashboard to Product

**Assignment 2: From Dashboard to Product**

## This week in plain words

Last week you built something for yourself. This week you build for someone else. That means planning first: who is it for, what problem does it solve, and what is the smallest version that proves the idea works. The written plan becomes the contract you hand to your AI, and the thing you point back to when it drifts.

## Key ideas

- **Models come in sizes.** Small models are fast and cheap, mid-tier models handle most coding, and top-tier models are best for big, tricky jobs. Pros pick a model for the task, not out of loyalty.
- **Models have personalities.** Some are stronger at clean code and design, some at deep reasoning, some at images and very long documents. Try more than one.
- **Why answers differ.** An AI predicts the next word (token) from a set of likely choices, with some randomness. That randomness is why two runs differ, and it's also where new ideas come from.
- **The old way vs the new way.** Software used to move from product manager to designer to developer to tester, one hand-off at a time. With AI, those steps collapse. The question shifts from "Can I build this?" to "Should I build this, and did I describe it clearly enough?"
- **Build the minimum (MVP).** Plan, define, then build the smallest version. The goal of an MVP is to learn fast, not to build everything.
- **The planning spectrum.** Match the planning to the stakes:
  1. *Quick chat* for exploring an idea.
  2. *Plan mode* for a new feature.
  3. *A PRD* (Product Requirements Document) for something real.
  4. *A full spec* for something that has to last.
- **Start by talking to the AI.** Describe your idea casually and let it ask you questions about audience, data and features. The AI becomes your product manager.
- **Spec-driven development.** Co-write the spec, tell the AI to build it, and point back to the spec whenever the code drifts.
- **The harness matters.** The same AI model can feel very different in a simple chat box than inside a full coding tool that can see your files. The tool around the model (the "harness") decides what it can do.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | Research, planning and build prompts for this week |
| [prd-architect.md](prd-architect.md) | How to use the PRD Architect to write your plan |
| [agents-md-build-rules.md](agents-md-build-rules.md) | An AGENTS.md rules file that keeps a chatbot on plan |
| [prd-architect skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect) | The same tool as an installable skill for Claude or ChatGPT |

---

## Assignment 2: From Dashboard to Product

**Tools:** Any AI you like for research (Claude, ChatGPT, Gemini, [NotebookLM](https://notebooklm.google.com)) · [PRD Architect](https://chatgpt.com/g/g-693b8b92a6f88191bac257f00fb49d57-prd-architect), [MVPunk](https://mvpunk.com), or [OpenSpec](https://openspec.dev) for your plan · Your vibe coding tool of choice

Last week you built a dashboard for yourself. This week you're building something for someone else. Find data, research it, plan it, scope it to the essentials, and build it.

> **The point of this assignment:** stop building for yourself and start building for a specific person. Who your user is should drive what you build. Don't just write a plan and then build whatever; let the plan change your product. By the end you should be able to point to a real decision, a feature you added, cut, or reshaped, that you made *because of who your user is*. That translation from idea to product decisions is the whole skill this week.

> **How to submit:** In your submission for this assignment, include all four:
>
> 1. Your plan (a share link, a GitHub Gist link, or the full plan text pasted into the box)
> 2. Your VibeIt link (publish your tool to VibeIt, then submit that link)
> 3. Your build outline
> 4. Your reflection (about 500 characters)

> **One project or four, your call.** Build on last week's work or start something new. You can carry one project through the whole course or treat each assignment as its own thing. Both are fine.

---

### 1. Find a Dataset

Pick a dataset that interests you. It should have enough depth that a stranger would find it useful or fun to explore. Even a few dozen rows works fine if there's variety. Some places to look:

[data.gov](https://data.gov) · [Kaggle](https://www.kaggle.com/datasets) · [Google Dataset Search](https://datasetsearch.research.google.com) · [World Bank](https://data.worldbank.org) · [FiveThirtyEight](https://github.com/fivethirtyeight/data) · or export something from an app you already use.

---

### 2. Research Your Data

Before you plan anything, explore what's actually in the data. Use whatever AI you like: [NotebookLM](https://notebooklm.google.com) is great for this, but Gemini, ChatGPT, and Claude all work too. Upload your dataset and try prompts like:

```text
What are the most surprising patterns in this data?
```

```text
If I were building a tool for [your target audience], what features would matter most based on this data?
```

```text
What questions would a first-time visitor want answered immediately?
```

```text
What story does this data tell that most people wouldn't notice on their own?
```

> **Feed less, smarter.** If your dataset is large, don't upload every row. Paste a summary, the column names, and a few sample rows instead. You'll get more grounded answers and won't burn through your usage limits.

---

### 3. Plan Your Product

Before you build anything, figure out what you're building and for whom. Start by talking to the AI as a planning partner.

> **This is the key difference from last week.** Last week you went straight to building. This week you plan first. The planning is the skill. Anyone can prompt an AI to build something. Knowing *what* to build and *who it's for* is what separates a useful tool from a demo.

```text
I have data about [topic]. Help me brainstorm product ideas that would be useful to [audience]. Not dashboards, actual tools people would use.
```

```text
I'm thinking about building [idea]. Ask me the hard questions a product manager would ask before greenlighting this.
```

```text
What's the simplest version of this idea that still proves it works?
```

---

### 4. Create Your Plan

Turn your thinking into a written plan you hand to your AI as the starting context. The plan covers the same four things no matter which tool you use: who it's for, the problem, the features, and what "done" looks like. You'll reuse this plan in Week 3 and the capstone. Pick the option that matches your comfort level and your build tool.

> **Default: PRD Architect + AGENTS.md.** Works in any chatbot, and the recommended path for most of you. The [PRD Architect](https://chatgpt.com/g/g-693b8b92a6f88191bac257f00fb49d57-prd-architect) GPT interviews you one question at a time and co-writes a PRD. Pair it with an [AGENTS.md](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0) rules file so the AI builds the way you want and doesn't drift from your plan.

> **Reach: MVPunk.** [MVPunk](https://mvpunk.com) outputs a five-file contract: your plan, agent rules, a design system, a project guide, and a START_HERE file. It's the most thorough option, but those five files are harder to feed into a plain chatbot, so it shines with Claude Code or a medium-level coding tool. Free to use. Enrolled students get a promo code in Canvas that unlocks the AI features for the term.

> **Advanced: OpenSpec.** For students comfortable in a code editor. [OpenSpec](https://openspec.dev) is an open-source, spec-driven framework that keeps a living spec and proposes each change as a delta, and it works with 20+ AI assistants with no lock-in. Use it if you want real version control over what you're building.

However you build it, your plan should cover:

* **Users:** Who is this for? Be specific. "Everyone" is not an answer.
* **Problem:** What does this person need or want that they can't easily get right now?
* **Features:** What does the tool actually do? List the core things a user can do on the page.
* **Success Criteria:** How do you know it works? What does "done" look like?

When it's done, grab a share link, put it in a GitHub Gist, or copy the full text. Canvas can't take file uploads for this one, so paste a link or the text itself into the submission.

### 5. Build It

Hand your plan to your vibe coding tool and use it as the starting context. When the AI drifts from what you defined, point it back to the plan.

**Suggested prompts for the build:**

```text
Here's my plan. Build the landing page first so we can get the user experience right before adding features.
```

```text
The current version doesn't match the plan. The user should see [X] when they arrive, not [Y]. Fix this.
```

```text
What would make someone bookmark this page and actually come back to it?
```

```text
Look at the plan again. What features haven't we built yet?
```

> **Frame it for a stranger.** A first-time visitor should understand what your tool is and how to use it without asking. Give it a title, a one-line summary of what it does, and labels that make sense cold. You know your data because you built it; they arrive with nothing.

**What NOT to build:** A dashboard that shows charts about your data. That's what you did last week. This time the output should be interactive, have a clear purpose for the visitor, and feel like a product, not a report.

**Project ideas (pick one or invent your own):** a lookup/search tool with detailed cards · a comparison tool that puts two things side by side · a recommendation engine ("I like X, what else would I like?") · a quiz or trivia game built from your data · a timeline or explorer that tells a story · a planning or decision tool that helps users make choices.

> **You are the QA.** Before you call it done, check it yourself: it loads from a fresh start, it works on a phone, and every control does something. The AI will say it's finished before it actually is.

---

### 6. Generate a Build Outline

Paste this into the same conversation where you built your tool:

```text
Review our conversation and create a short outline of what we built together. No more than 10 bullet points, each under 150 characters. Focus on what was built or changed, not the prompts I typed.
```

Copy the result and paste it into your Canvas submission.

---

### 7. Publish It to VibeIt

> **Test your link before you submit.** Open your published VibeIt link in a private or incognito window. If it doesn't load there, it won't load for me. A broken link is the most common reason work doesn't count.

Add your finished tool to [VibeIt](https://vibeit.work) (public or private, your choice) and submit your VibeIt link. Public entries show up in the class gallery.

---

### 8. Write a Short Reflection

500 characters or less. Name one decision you made *because of who your user is*: a feature you added, cut, or changed. How did planning first change the way you worked? Keep it casual.

---

### Checklist

|  |  |
| --- | --- |
| ☐ | Find a dataset that supports a consumer-facing tool |
| ☐ | Explore the data in the AI tool of your choice |
| ☐ | Plan your product by talking through the idea with AI |
| ☐ | Create a plan (PRD Architect, MVPunk, or OpenSpec) with clear users, problem, features, and success criteria |
| ☐ | Scope down to the essential features only |
| ☐ | Build a working prototype using your plan as the starting context |
| ☐ | Tool has a clear purpose visible to a first-time visitor |
| ☐ | Publish to VibeIt (public or private, your choice) |
| ☐ | Generate your build outline using the prompt in step 6 |
| ☐ | Write your short reflection |
| ☐ | Test your published link in a private window to confirm it loads |
| ☐ | **Submit:** your plan, VibeIt link, build outline, and reflection |

---

### Completion

No grades. The certificate is based on attending the sessions; assignments should be submitted and up to date too.

---

### Tips

* **Start with the data, not the code.** Research your dataset in any AI first. Understanding your data is half the work.
* **The plan is the skill.** The grading leans toward the clarity of your plan and concept, not how polished the code is.
* **Describe what's wrong.** "The search results don't filter correctly when I type a name" beats "fix it." Screenshots often work even better than descriptions.
* **Start fresh if things break.** If the AI stops following instructions, open a new chat and paste your plan back in as context.
* **Save often.** Download your work as you go.
* **Use the Class Q&A and Help discussion for help.** Don't contact me directly. Post in the discussion so everyone benefits from the answers.

---

## Sources

- Assignment 2 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, Part 2: From Dashboard to Product.
- Gist: [An AGENTS.md file for chatbots to use when building apps](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0), copied into [agents-md-build-rules.md](agents-md-build-rules.md).
- [PRD Architect](https://chatgpt.com/g/g-693b8b92a6f88191bac257f00fb49d57-prd-architect), a custom GPT linked from the assignment.

[Back to the main index](../README.md)
