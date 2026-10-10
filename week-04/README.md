# Week 4: The AI Powered App

**Assignment 4: Gamification & Design Principles**

## This week in plain words

This week covers the developer ideas behind the tools you've been using (databases, logins, APIs, keys and costs) and the design principles that make people want to stay. You'll apply at least two of those principles to a game or to a project you already built, and be able to point to exactly where each one shows up.

## Key ideas

### How apps work under the hood

- **Databases.** Almost everything an app does with data is one of four actions: create, read, update, delete (CRUD). Some databases use strict tables (SQL), some store flexible documents (NoSQL), and some store meaning for AI search (vector).
- **Authentication vs authorization.** Authentication is *who you are* (logging in). Authorization is *what you're allowed to see or do* (roles and permissions). People mix them up all the time.
- **APIs and JSON.** An API is like a waiter: your app orders, the server's kitchen cooks, and the waiter brings back the result. That result usually comes packaged as JSON, a simple, structured list of labels and values.
- **MCP (Model Context Protocol).** A standard way for AI agents to plug into outside tools and data, like a USB-C port for AI. Treat a new MCP server like any other software you install, because it can touch your files and accounts.
- **API keys are passwords that decide who gets charged.** Keep them out of your code, your chats and GitHub. Use the tool's key settings and set spending limits.
- **Backend as a Service.** Platforms like Firebase and Supabase bundle the database, logins and storage, so you don't run your own server. Free tiers are generous. Set billing alerts everywhere.
- **Measure what matters.** Track daily active users, how many come back (retention), and how many reach the core feature (activation). You can't improve what you don't measure.

### Design principles (the heart of Assignment 4)

- **The first minute.** Show value fast and give a small win before asking for anything. The best onboarding is the product doing something delightful.
- **Progression.** Start simple, teach one thing at a time, and unlock more as people learn. Too hard is frustrating, too easy is boring. The sweet spot is called flow.
- **Story and stakes.** Give people an emotional reason to come back and something to gain or lose. Story doesn't have to mean a narrative.
- **Feedback loops.** Every action should get a visible response: clicks animate, saves confirm, errors explain. A silent interface feels broken.
- **Gamification.** Progress bars, streaks, levels and "one more turn." Ship the core experience first. Gamification is a layer on top of real value, not a substitute for it.

### Google AI Studio

AI Studio lets you build apps that use Gemini features: text, vision, image generation, audio, live voice, maps and search. It manages your Gemini API key for you, so you never paste a real key into your code. Its app gallery is full of small demos you can remix.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | Planning and build prompts for Path A (game) and Path B (add principles) |
| [security-test-step-DRAFT.md](security-test-step-DRAFT.md) | **DRAFT.** A proposed extra step: security test your live site |
| [security-test-prompt-DRAFT.md](security-test-prompt-DRAFT.md) | **DRAFT.** The proposed Security Test Prompt for that step |
| [security-check skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/security-check) | The same tool as an installable skill for Claude or ChatGPT |

> **Heads up:** the two DRAFT files are proposals that are not yet part of the official assignment. Follow the assignment steps below unless your instructor says otherwise.

---

## Assignment 4: Gamification & Design Principles

**Tools:** Default path builds a game in [Google AI Studio](https://aistudio.google.com). Or apply the principles to a site you already built, using any tool you like.

This week is about the design and gamification principles from class: the first minute, progression, story and stakes, feedback loops, and gamification. They make any product better, not just games. Your job is to apply at least two of them to something real and explain what you did.

> **The point of this assignment:** the principles are the assignment, not the game. Pick at least two and apply them so deliberately that you can point to exactly where each one lives. "I added a progress bar in the header and the first screen teaches the controls" is the goal. "I made it fun" is not. Naming where a principle shows up is how you show you actually used it.

> **One project or four, your call.** You can treat the course as one project you grow week to week, or build a separate project for each assignment. Both are fine. For this one, "build upon an earlier project" and "start something new" are equally welcome. Do whatever keeps you motivated.

> **How to submit:** Answer the questions below. There is a **separate box for each item**:
>
> 1. Your VibeIt **app** link (publish your game or site to VibeIt, then submit that link, not a profile ID)
> 2. Your build outline
> 3. Your reflection (about 500 characters), naming which principles you applied

> **Test your link before you submit.** Open your published VibeIt link in a private or incognito window. If it doesn’t load there, it won’t load for me. A broken link is the most common reason work doesn’t count.

---

### 1. Pick Your Path

Two ways to do this assignment. Pick the one that fits you. The learning goal is the same either way: apply the principles and be able to point to where.

**Path A: Build a Game (the fun one).** Games make the principles impossible to ignore. You feel it the instant a feedback loop is missing or the difficulty curve is wrong. Build a real game in AI Studio, the kind where things move, collide, and respond.

**Path B: Add Principles to Your Project.** Prefer to keep building something real? Take your dashboard, product, or app from an earlier week (or a new site) and layer in at least two principles: a feedback loop, a progression that unlocks over time, a first minute that teaches itself, a streak or progress bar. Same principles, applied to a product instead of a game.

---

### 2. The Principles (both paths target these)

* **The first minute.** Show value fast. Give a small win before asking for anything. Teach as the user plays instead of front-loading instructions.
* **Progression.** Layer complexity over time. Start easy, introduce one new element at a time, keep people in the flow state between bored and overwhelmed.
* **Story and stakes.** Give the user a reason to care and something to gain or lose, even without a literal narrative.
* **Feedback loops.** Every action gets a visible response. Clicks animate, saves confirm, errors explain. Silent interfaces feel broken.
* **Gamification.** Progress bars, streaks, levels, "one more turn." A layer on top of real value, not a substitute for it.

> **You've already used these.** The [Vibe Glossary's](https://vibeglossary.com) VibeScore (points, levels from Lurker to Vibe Coder, streaks, and learning-path badges) is a live example of every principle on this list. Open it and notice how it pulls you forward, then borrow what works for your own project.

---

### 3A. Path A: Build It in AI Studio

Think arcade, not worksheet: real-time action, physics, or spatial reasoning. Plan first in a chatbot (planning is free, Build mode uses credits), then build in [AI Studio](https://aistudio.google.com).

```text
I want to build a [describe your game] using [Three.js / Phaser 4 / Canvas]. Help me plan the game loop, controls, scoring, and level progression. What happens in the first 5 seconds? How does the difficulty ramp? Ask me questions and brainstorm with me.
```

```text
Build a [describe your game] using [Three.js / Phaser 4 / HTML Canvas]. Start with a splash screen and clear instructions. Use keyboard or touch controls. Include collision detection, a score system, particle effects on impact, and at least three stages of increasing difficulty.
```

**Try to include at least one advanced feature:** a 3D scene or real game engine, two-player or a shared leaderboard, saved high scores via Firebase, a Google feature like Maps, or voice/camera input through the Live API.

---

### 3B. Path B: Add Principles to Your Project

Open a project you already built, or start a fresh site, and add at least two of the principles above. Aim for changes a visitor would actually feel.

```text
Add a first-minute experience: the moment someone lands, show one real result or a small win before asking them to sign up or fill anything in.
```

```text
Add feedback loops: make every action produce a visible response. Confirmations on save, animations on click, clear explanations on error.
```

```text
Add progression or gamification: a progress bar, a streak, levels, or a completion meter that rewards people for coming back.
```

---

### 4. Looking Ahead: Optional Stretch (A5)

Whatever you build here can carry into **Assignment 5: Optional Stretch: Ship Checklist** if you want gallery glory or more finishing practice. A5 is **not** required for the Certificate. Optional professional tooling (GitHub, Claude Code, agents) lives there too; don't feel you need to go deep on workflow yet. For now, focus on the principles and the ship-for-a-stranger gate below.

---

### 5. Publish It and Add It to VibeIt

Publish your game or site to a live URL and test it in a new browser. Play or click through it. Make sure it actually works for someone who isn't you. Then add it to [VibeIt](https://vibeit.work) (public or private, your choice) and submit your VibeIt **app** link.

> Heads up on AI Studio publishing: deploying a game can require enabling billing on Google Cloud, and Publish is occasionally blocked by region. If Publish fails, use **Share** instead and turn on access for anyone with the link, then say so in your submission. Test the live link before you submit.

---

### 6. Generate a Build Outline

Paste this into the same conversation where you built:

```text
Review our conversation and create a short outline of what we built together. No more than 10 bullet points, each under 150 characters. Focus on what was built or changed, not the prompts I typed.
```

---

### 7. Reflect

500 characters or less. Name the two principles you applied and point to exactly where in your project each one shows up. What changed about how it feels? Keep it casual.

---

### Ship for a stranger (required)

Before you check the list below, confirm these three. This polish gate is part of the Certificate path (A1–A4).

* **Live URL works in a private/incognito window**: open it logged out / private so you're not seeing a cached logged-in version.
* **VibeIt link is the app entry**: the link that opens your project for a stranger, not a profile ID.
* **One sentence on first impression**: what a stranger sees in the first few seconds (put it in your reflection or outline).

---

### Checklist

|  |  |
| --- | --- |
| ☐ | Pick a path: build a game (Path A) or add principles to a project (Path B) |
| ☐ | Apply at least two design principles (first minute, progression, story/stakes, feedback loops, gamification) |
| ☐ | Plan first in a chatbot, then build |
| ☐ | **Ship for a stranger:** private-window live URL, VibeIt app link, one-sentence first impression |
| ☐ | (Optional later) Note a project you might polish in A5 stretch, not required for the Certificate |
| ☐ | Publish with a live URL, test it, and add it to VibeIt (public or private) |
| ☐ | Generate your build outline |
| ☐ | Write your reflection naming the principles you applied |
| ☐ | **Submit:** your VibeIt app link, build outline, and reflection |

---

### Completion

No grades. Soft deadlines. **A4 is on the Certificate path:** Certificate = attend sessions + **A1–A4 submitted and up to date**. **A5 is an optional stretch** afterward: gallery glory / finishing practice, not required for the Certificate.

---

## Sources

- Assignment 4 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, Part 4: The AI Powered App.
- Draft security test prompt and step text written for this course. **Not yet approved.** See the DRAFT files.

[Back to the main index](../README.md)
