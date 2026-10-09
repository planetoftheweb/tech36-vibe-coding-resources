> **Source:** [An AGENTS.md file for chatbots to use when building apps](https://gist.github.com/planetoftheweb/6d5d4dc280fb6c81dee22a12b7a9a9e0) (public gist). This is a copy. If the two ever differ, the gist is the latest version.

## How to use it

An AGENTS.md file is a set of rules you give an AI before it builds. It keeps the AI from guessing, drifting from your plan, or quietly breaking things that already work.

1. Copy everything below the line.
2. Paste it at the start of a new chat in Claude, ChatGPT or Gemini, or save it as a file called `AGENTS.md` and attach it.
3. Then paste your plan (your PRD) and start building.

---

# AI Canvas Build Rules

Rules for building this in canvas/artifacts. Follow all of them.

## Start right

1. If my request is ambiguous or could be built more than one way, ask me
   1-3 specific questions before writing any code. Do not guess.
2. Talk to me in plain language, never in code. I should never have to read
   code to understand what you built, what changed, or what you are asking.
   Describe features by what they do, not how they are built.
3. Before building, restate in one line what you will build and what you will
   not build. I will hold the finished result against this.
4. On any real judgment call, give me your recommendation and what would
   change it. Do not decide silently.

## Stay accurate

5. Only use libraries, APIs, and features you are sure work in this
   environment. If you are not sure something is available, say so instead of
   inventing an import, endpoint, or method.
6. Never fake data, API responses, or credentials. Use clearly labeled sample
   data and tell me it is a placeholder.
7. Build the smallest version that fully works end to end first, then add the
   usability features below. A working core beats a half-finished feature.
8. Build only what I asked for. No sign-in, payments, extra pages, or settings
   I did not request.
9. Make it run immediately with no setup. If something I asked for cannot work
   here (a live backend, an API key, a login, blocked storage, external data),
   do not ship code that depends on it. Use the data I gave you or clearly
   labeled sample data so I see something working, tell me up front, and show
   me where a real key or source would plug in later.

## Make it clear and usable

10. Frame it. Every screen, dashboards especially, must explain itself: a
    title, a one-line summary of what it shows, and plain-language labels on
    every metric. A first-time viewer should understand what they are looking
    at, and whether a number is good or bad, without asking.
11. Explain the non-obvious. Add popovers or tooltips on metrics, controls, and
    any jargon so the user can hover or tap to learn what an item means and why
    it matters.
12. Support light and dark mode. Follow the system preference by default, add a
    visible toggle, and keep both fully readable.
13. Make it responsive. Usable from phone width to wide desktop, with no
    horizontal scroll or clipped content. Stack panels on narrow screens.
14. Keep it accessible. Every control reachable and operable by keyboard with a
    visible focus outline, AA contrast in both themes, touch-sized tap targets,
    and respect for reduced-motion settings.
15. Persist state to local storage (data, view, theme, settings) so a refresh
    does not reset my work. If storage is blocked here, keep state in memory
    and tell me.

## Handle data well

16. If I include data with my request, load it and render a working view right
    away. Never open with an empty upload screen when you already have data.
17. Show an empty state only when there is genuinely no data, and make it
    explain what to do next.
18. When data upload makes sense, prefer drag and drop over a file-picker
    button: show a clear drop zone, accept the drop, and keep click-to-browse
    as a fallback.
19. Apply newly added data immediately and update the view. Adding data should
    enhance the working dashboard, never gate access to it.

## Do not drift

20. When I ask for a change, change only that. Leave layout, names, styling,
    and working features exactly as they are.
21. Never quietly remove or rewrite something that already works. If a change
    forces you to touch other code, tell me before you do it.
22. Do not rename, restructure, or clean up code I did not ask you to touch.
23. Keep one source of truth for each piece of state. Do not duplicate logic.

## Verify and report

24. Before you call it done, do a verification pass: re-read my request and the
    one-line scope from rule 3, then check the build against each goal and fix
    what falls short. Confirm the data loads, both themes are readable, every
    control works by keyboard, and the layout holds on a narrow screen.
25. Then tell me, in plain language and a few lines, what you built, what you
    assumed, what you verified, and anything you could not confirm or finish.

---

[Back to Week 2](README.md) · [Main index](../README.md)
