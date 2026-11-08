# Week 2: From Dashboard to Product

**Assignment 2: From Dashboard to Product**

## This week in plain words

Last week you built something for yourself. This week you build for someone else. That means planning first: who is it for, what problem does it solve, and what is the smallest version that proves the idea works. The written plan becomes the contract you hand to your AI, and the thing you point back to when it drifts.

## Key ideas

- **Models come in sizes.** Small models are fast and cheap, mid-tier models handle most coding, and top-tier models are best for big, tricky jobs. Pros pick a model for the task, not out of loyalty.
- **Models have personalities.** Some are stronger at clean code and design, some at deep reasoning, some at images and very long documents. Try more than one.
- **Why answers differ.** An AI predicts the next word (token) from a set of likely choices, with some randomness. That randomness is why two runs differ, and it's also where new ideas come from.
- **The old way vs the new way.** Software used to move from product manager to designer to developer to tester, one hand-off at a time. With AI, those steps collapse. The question shifts from "Can I build this?" to "Should I build this, and did I describe it clearly enough?"
- **Build the minimum ([MVP](https://vibeglossary.com/build/mvp)).** Plan, define, then build the smallest version. The goal of an MVP is to learn fast, not to build everything.
- **The planning spectrum.** Match the planning to the stakes:
  1. *Quick chat* for exploring an idea.
  2. *Plan mode* for a new feature.
  3. *A [PRD](https://vibeglossary.com/build/prd)* (Product Requirements Document) for something real.
  4. *A full spec* for something that has to last.
- **Start by talking to the AI.** Describe your idea casually and let it ask you questions about audience, data and features. The AI becomes your product manager.
- **Spec-driven development.** Co-write the spec, tell the AI to build it, and point back to the spec whenever the code drifts.
- **The harness matters.** The same AI model can feel very different in a simple chat box than inside a full coding tool that can see your files. The tool around the model (the "harness") decides what it can do.

## Slide takeaways: the big shifts this week

These points come from the Week 2 class session. Screenshots aren't included here, but the ideas are what matter. Each one connects to something you'll do in the assignment.

### Pick a specific audience and a useful outcome

"Everyone" is not a target user. Your product needs a person you can describe and a reason they'd come back. That combination, a specific audience plus a clear outcome, is your value proposition. The [Vibe Glossary entry on personas](https://vibeglossary.com/build/personas) walks through how to think about who you're building for.

### Product-market fit has to be tested, not assumed

A polished prototype can feel convincing, but looking good is not the same as being useful. The only way to know if your idea solves a real problem is to put it in front of someone and watch what happens. Don't confuse "I built a nice thing" with "someone needs this thing."

### A first-time visitor has no context

You've been living inside your project. A stranger arrives with no chat history, no memory of your planning conversations, and no idea what your tool does. Design for that cold start. If it doesn't make sense on the very first load, it doesn't work yet.

### Show the main action and what it gets the visitor

Don't list every feature on the landing screen. Lead with what the tool does and what the visitor walks away with. Think in terms of [jobs to be done](https://vibeglossary.com/build/jtbd): what did this person come here to accomplish?

### Remove friction and confusing labels

If a button says something only you understand, rename it. If a visitor has to figure out where to start, you haven't finished designing the entry point. Clear labels and obvious next steps beat clever names every time.

### Modern and AI-native does not mean chatbot

You can build something that feels current and smart without adding a conversational interface. A recommendation engine, a smart search, or a personalized filter can all feel AI-native. Pick the interaction pattern that fits your use case, not the one that sounds most impressive.

### Build the minimum first

An [MVP](https://vibeglossary.com/build/mvp) is the smallest version that still proves the idea works. Get that running end to end before adding extras. You'll learn more from a simple thing that works than from a complex thing that doesn't.

### Let the AI interview you to clarify your plan

Instead of staring at a blank page, tell the AI your idea and let it ask you questions. It can help you pin down your users, the problem you're solving, the core features, and your [success criteria](https://vibeglossary.com/build/acceptance-criteria). That back-and-forth conversation becomes the plan you hand to your coding tool.

### User feedback changes the product

The plan you write before building is not a contract you're locked into forever. When you test with someone, or even just look at your tool through fresh eyes, you'll see things to cut, add, or reshape. That's the process working, not a sign you planned badly.

### Make the AI prove it's done with real tests

The AI will tell you it's finished before it actually is. Don't take its word for it. Open the tool in a private window. Tap every button. Load it on your phone. You verify the actual behavior in the browser, because that's the only thing that counts.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | Research, planning and build prompts for this week |
| [prd-architect.md](prd-architect.md) | How to use the PRD Architect to write your plan |
| [agents-md-build-rules.md](agents-md-build-rules.md) | An AGENTS.md rules file that keeps a chatbot on plan |
| [prd-architect skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect) | The same tool as an installable skill for Claude or ChatGPT |

---

## Assignment 2: From Dashboard to Product

**Tools:** Any AI you like for research (Claude, ChatGPT, Gemini, [NotebookLM](https://notebooklm.google.com)) · [PRD Architect skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect), [MVPunk](https://mvpunk.com), or [OpenSpec](https://openspec.dev) for your plan · Your vibe coding tool of choice

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

> **Default: PRD Architect + AGENTS.md.** Works in any chatbot, and the recommended path for most of you. The [PRD Architect skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect) interviews you one question at a time and co-writes a PRD. Install it in Claude, or paste it into a ChatGPT Project. Pair it with an [AGENTS.md](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0) rules file so the AI builds the way you want and doesn't drift from your plan.

> **Reach: MVPunk.** [MVPunk](https://mvpunk.com) outputs a five-file contract: your plan, agent rules, a design system, a project guide, and a START_HERE file. It's the most thorough option, but those five files are harder to feed into a plain chatbot, so it shines with Claude Code or a medium-level coding tool. Free to use. Enrolled students get a promo code in Canvas that unlocks the AI features for the term.

> **Advanced: OpenSpec.** For students comfortable in a code editor. [OpenSpec](https://openspec.dev) is an open-source, spec-driven framework that keeps a living spec and proposes each change as a delta, and it works with 20+ AI assistants with no lock-in. Use it if you want real version control over what you're building.

However you build it, your plan should cover:

* **Users:** Who is this for? A [persona](https://vibeglossary.com/build/personas) helps you get specific. "Everyone" is not an answer.
* **Problem:** What does this person need or want that they can't easily get right now? Think about their [job to be done](https://vibeglossary.com/build/jtbd): what are they trying to accomplish?
* **Features:** What does the tool actually do? List the core things a user can do on the page.
* **Success Criteria:** How do you know it works? What does "done" look like? Writing clear [acceptance criteria](https://vibeglossary.com/build/acceptance-criteria) makes this concrete.

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

## Top FAQs for this assignment

Skim the headings and jump to what you need. These cover the questions that come up most often.

### Can I keep working on my Week 1 project?

Yes. You can continue your last project or start something completely new. Some people carry one project through the whole course; others start fresh each week. Both paths are completely fine. Do whatever keeps you motivated.

### Which vibe-coding tool should I use?

Whatever you prefer. Claude, ChatGPT, Gemini, Lovable, Cursor, or anything else that lets you describe what you want and get working output. This week there's no required tool.

### Which planning tool should I pick?

**Default:** [PRD Architect](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect) paired with an [AGENTS.md](agents-md-build-rules.md) rules file. Works in any chatbot. Recommended for most people.

**Reach:** [MVPunk](https://mvpunk.com). Outputs a five-file contract. More thorough, but those files work best with a coding tool like Claude Code.

**Advanced (optional):** [OpenSpec](https://openspec.dev). For people comfortable in a code editor who want version control over their spec.

All three cover the same four things. Pick the one that matches your comfort level.

### What does the plan need to cover?

Four things:

1. **Users:** who it's for (a [persona](https://vibeglossary.com/build/personas), not "everyone")
2. **Problem:** what they need that they can't easily get right now
3. **Core features:** what the tool actually does
4. **Success criteria:** how you know it works (your [acceptance criteria](https://vibeglossary.com/build/acceptance-criteria))

The [PRD glossary entry](https://vibeglossary.com/build/prd) breaks down what a product requirements document looks like.

### My dataset is huge. Do I upload the whole thing?

No. Paste the column names, a summary of what the data covers, and a handful of sample rows. You'll get better, more grounded answers from the AI, and you won't burn through your usage limits.

### Does my tool have to be interactive?

Yes. A page of charts about your data is what you built in Week 1. This time, the tool should be interactive and have a clear purpose for the visitor. A stranger should land on it and immediately understand what it does, not just see a collection of charts.

### How do I submit my plan? Can I upload a file?

No file uploads for this one. Submit your plan as a share link, a GitHub Gist link, or paste the full text directly into the submission box.

### What exactly do I submit?

Four pieces:

1. **Your plan** (share link, Gist link, or pasted text)
2. **Your VibeIt link** (publish your tool to [VibeIt](https://vibeit.work), then submit that link)
3. **Your build outline** (generated with the prompt in [step 6](#6-generate-a-build-outline))
4. **Your reflection**

### What goes in the build outline?

A short list of what you built or changed during the session. Focus on outcomes, not the prompts you typed. Max 10 bullet points, each under 150 characters.

### What goes in the reflection?

Name one decision you made because of who your user is: a feature you added, cut, or changed. Then say how planning first affected the way you worked. Keep it short and casual.

### Can my VibeIt entry be private?

Yes. Public or private, your choice. Public entries show up in the class gallery. Either way, test your submitted link in a private or incognito window to make sure it actually loads.

### How do I know my tool actually works?

Open your published link in a private or incognito window. Check that it loads from a completely fresh start, works on a phone, and every button and control does something visible. You are the QA team. If the AI says it's done, verify that yourself before submitting.

---

## Common pitfalls

Real problems that have come up (no names, just the patterns). If you see yourself here, you're not alone, and they're all fixable.

### Submitted a slideshow instead of a working tool

The assignment asks for an interactive tool published to VibeIt, not a presentation or a set of slides. If your link opens a slideshow, go back and build the actual product. The tool should do something when a visitor interacts with it.

### Data only shows up when you're signed in

If your tool requires a login to see anything, a visitor in a private window will see a blank page. Make sure the core experience works without signing in, or at least give visitors something useful before asking them to create an account.

### Link doesn't load in a private window

This is the single most common reason work doesn't count. Always test your submitted link in a private or incognito window before you call it done. If it doesn't load there, it won't load for anyone reviewing it.

---

## You've got this

This assignment is where things start to click. You're not just making something that looks cool anymore. You're thinking about who it's for, what they need, and how you'll know it works. That shift from "build a thing" to "build the right thing" is the whole point of this week.

If you get stuck, post in the [Class Q&A discussion](https://canvas.stanford.edu/courses/233860/discussion_topics/1287744) (Canvas login required). Everyone benefits when questions and answers are shared.

---

## Course links for this week

These links point to the live Canvas course site and require a Stanford login. They're listed here so you can jump straight to what you need. If you're reading this guide outside the course, the assignment steps above cover the same material.

| Link | What it is |
| --- | --- |
| [Assignment 2 page](https://canvas.stanford.edu/courses/233860/assignments/814038) | The active assignment on Canvas |
| [Submission quiz](https://canvas.stanford.edu/courses/233860/quizzes/191549) | Where you submit your four pieces |
| [Class Q&A discussion](https://canvas.stanford.edu/courses/233860/discussion_topics/1287744) | Post questions here so everyone benefits |
| [Week 2 slides](https://docs.google.com/presentation/d/1kWzVwAwafEjY6F2zJqn5OreYuGV8H6J3txdEcHUZkyY/edit?usp=sharing) | Google Slides, no login needed |

---

## Sources

- Assignment 2 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, [Part 2: From Dashboard to Product](https://docs.google.com/presentation/d/1kWzVwAwafEjY6F2zJqn5OreYuGV8H6J3txdEcHUZkyY/edit?usp=sharing) (Google Slides).
- Gist: [An AGENTS.md file for chatbots to use when building apps](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0), copied into [agents-md-build-rules.md](agents-md-build-rules.md).
- The [prd-architect skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/prd-architect), which replaces the PRD Architect tool linked from the assignment.

[Back to the main index](../README.md)
