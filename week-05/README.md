# Week 5: Professional Agentic Harness

**Assignment 5: Optional Stretch: Ship Checklist**

## This week in plain words

This week shows what building a real product looks like, using the story of an app built and shipped in about a week, and then tours the professional tools that make that possible. The optional assignment asks you to take one project from "a demo that works" to "a real thing I'd show someone."

## Key ideas

### Lessons from shipping a real product

- **Hand your AI a contract, not an idea.** Vague ideas make vague apps. Give it four files: a PRD (what to build), agent rules (how to behave), a design system (how it should look) and project context (how the pieces fit).
- **Real progress is lots of tiny commits.** Small, reversible changes let you try an idea, check the result, and undo it if it doesn't work. Build the answer instead of guessing it.
- **Logins are the milestone.** Adding accounts is where a toy becomes a product.
- **Wiring is the hard part.** Connecting an AI API is where beginners hit walls: model choices, keys and timeouts. The demo is easy, the deployment is the work.
- **Not every suggestion is a yes.** Listen to feedback, then decide. The core idea is yours to protect.
- **Remove friction before asking for commitment.** Let people try the product before they sign up.
- **Never trust the browser.** If something matters, like money or private data, the server has to enforce it. Lock the data, not the door.
- **Automate the checklist you'll forget.** Small automatic checks before each commit and push catch problems early.
- **The last ten percent looks professional.** A real domain, social preview cards, icons and links that keep working. Polish reads as trust.

### Professional tools, in plain words

- **GitHub is more than storage.** It has issues, project boards, pull requests, code review, automation (Actions) and releases.
- **AI in the GitHub workflow.** AI can write the change, describe the pull request, fix failing tests and walk you through merges. A human still owns the merge button.
- **A repo's paperwork.**
  - README: how to install and run it.
  - LICENSE: MIT is permissive, Apache 2.0 adds patent protection, GPL requires sharing changes.
  - CHANGELOG: what changed.
  - .gitignore: keeps secrets and build files out.
  - CONTRIBUTING: how others can help.
- **The tool landscape.** AI-aware editors (Cursor, VS Code) and command-line agents (Claude Code, Codex CLI, Gemini CLI).
- **Rules and memory.** Rules are what you tell the agent once, in a file it reads every time (like CLAUDE.md or AGENTS.md). Memory is what it learns and remembers across conversations.
- **Slash commands, skills, plugins and hooks.** These are reusable shortcuts and add-ons that extend what an agent can do and control how it does it.
- **Subagents and parallel work.** A main agent can hand jobs to helpers (explorer, planner, reviewer, tester), and git worktrees let two agents work in the same repo at once.
- **Background and cloud agents.** Let agents run long jobs while you keep working, locally or on a remote machine.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | The polish prompt and the "what I did to finish it" outline prompt |
| [ship-and-privacy-steps-DRAFT.md](ship-and-privacy-steps-DRAFT.md) | **DRAFT.** Proposed extra steps: ship pages and repo files, then a privacy check |
| [ship-files-prompt-DRAFT.md](ship-files-prompt-DRAFT.md) | **DRAFT.** The proposed Ship Pages and Repo Files Prompt |
| [privacy-test-prompt-DRAFT.md](privacy-test-prompt-DRAFT.md) | **DRAFT.** The proposed Privacy and Data Test Prompt |
| [privacy-check skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/privacy-check) | The same tool as an installable skill for Claude or ChatGPT |
| [ship-files skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/ship-files) | The same tool as an installable skill for Claude or ChatGPT |

> **Heads up:** the DRAFT files are proposals that are not yet part of the official assignment. Follow the assignment steps below unless your instructor says otherwise.

---

## Assignment 5: Optional Stretch: Ship Checklist

**Optional stretch: not required for the Certificate.** Tools: whatever you've already been using. Core: polish and publish. Advanced (optional): GitHub, Claude Code or Cursor, and the agentic tools from Part 5.

**This assignment is optional.** The Certificate does **not** require A5. It's here for students who want gallery glory, finishing practice, or one more pass at shipping something a stranger would actually open. If you stop after A4 with sessions attended, you're on the Certificate path.

If you do take it on: pick one thing you've built in this course and take it the rest of the way: from "a demo that works" to "a real thing I'd show someone." You are not starting over. You are finishing.

> **The point (if you choose it):** finishing is its own skill. The last ten percent, the first impression, the trust details, the thing actually working for a stranger, is what turns a demo into something real. Ship it like someone you respect is about to open the link.

> **Build on what you have.** Use your dashboard, your product, your Lovable app, or your game from any earlier week. Pick the one you like most or the one closest to being real. Starting fresh is allowed but not expected. The point is to ship, not to pile on more work.

> **How to submit (if you do this stretch):** Answer the questions below. There is a **separate box for each item**:
>
> 1. Your VibeIt **app** link (publish your finished project to VibeIt, then submit that link)
> 2. A short "what I did to finish it" outline
> 3. Your reflection (about 500 characters)

> **Test your link before you submit.** Open your published VibeIt link in a private or incognito window. If it doesn’t load there, it won’t load for me. A broken link is the most common reason work doesn’t count.

---

### 1. Pick Your Project

Choose one project from the course. Best candidates are the ones that already mostly work and that you actually care about. If two weeks ago you built something you're proud of, this is where it becomes real.

---

### 2. Core Track: Finish and Polish

The last ten percent is what separates a demo from a product. Pick the items that apply and make your project feel finished:

* **First impression.** A clear title, a one-line description of what it does, and a real first-minute experience. A new visitor should "get it" without you explaining.
* **The details that read as trust.** A favicon and page title, a social preview image, an About section, working links, no dead buttons.
* **It actually works for someone else.** Test the live site in a private window or on your phone. Try the main flow start to finish as if you were a stranger.
* **One real improvement.** Fix the roughest edge, or add the one feature that was missing. Your call.

```text
Look at my project like a first-time visitor who has never seen it. List the five things that make it feel unfinished or confusing, then help me fix them one at a time.
```

---

### 3. Advanced Track (optional)

☐ **Optional:** try one pro-tool step (GitHub commit + README, a change in Claude Code/Cursor, an agent-assisted tweak, or a tiny test/pre-commit check). Skip freely; core polish alone completes this stretch.

---

### 4. Publish It and Add It to VibeIt

Get it onto a real, public URL and test the live version. If you used a custom domain or set up hosting yourself, even better. Make sure the link works for someone who is not logged into your accounts. Then add it to [VibeIt](https://vibeit.work) and submit your VibeIt app link. **Making your entry public is encouraged** so your finished project joins the class gallery, but private is fine if you'd rather not share.

---

### 5. Write Your "What I Did to Finish It" Outline

A short list of what you changed to take this from demo to done. If you tried the advanced checkbox, say what you did and how it went. You can ask your AI tool to draft it:

```text
Review our conversation and create a short outline of what we changed to finish this project. No more than 10 bullet points, each under 150 characters. Focus on what was polished, fixed, or added.
```

---

### 6. Reflect

500 characters or less. What did "finishing" actually take? What surprised you about the last ten percent? Keep it casual.

---

### The Class Gallery

Make your VibeIt entry public and your finished project joins the class gallery, where everyone can see what the group built. Browsing each other's work is one of the best parts of the course, and a great way to end. You can also drop a note in the class discussion to point people to it.

---

### Checklist

|  |  |
| --- | --- |
| ☐ | (Optional stretch) Pick one project from the course to finish |
| ☐ | Core: polish the first impression, the trust details, and the main flow |
| ☐ | Make at least one real improvement |
| ☐ | (Optional) One advanced-track checkbox: GitHub / Claude Code / agent / tiny test |
| ☐ | Publish, test the live URL as a stranger would, and add it to VibeIt (public encouraged) |
| ☐ | Write your "what I did to finish it" outline |
| ☐ | Write your reflection |
| ☐ | **Submit:** your VibeIt app link, finish outline, and reflection |

---

### Completion

**This assignment is explicitly optional.** No grades. Soft deadlines. The **Certificate** = attend sessions + **A1–A4 submitted and up to date**. A5 does **not** gate the Certificate; do it only if you want the stretch / gallery finish.

---

## Sources

- Assignment 5 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, Part 5: Professional Agentic Harness.
- Draft ship files prompt, privacy test prompt and step text written for this course. **Not yet approved.** See the DRAFT files.

[Back to the main index](../README.md)
