# Week 3: The App Development Spectrum

**Assignment 3: The App Development Spectrum**

## This week in plain words

Chatbots are great at single-page demos, but real apps need a server. A server remembers things between visits, decides who can see what, and connects to outside services. This week you cross that wall with Lovable, a no-code platform that gives you a database, logins and one-click publishing. Then you have an AI user test your live site like a stranger would.

## Key ideas

- **The chatbot wall.** A chatbot demo is one page with no server. A real product needs logins, saved data, file storage and sometimes payments. Those live on a server.
- **Every website speaks three languages.** HTML is the structure, CSS is the style, and JavaScript is the behavior. Browsers only understand these three.
- **The invisible build step.** AI tools often write code in a framework like React. A build step quietly translates it into plain HTML, CSS and JavaScript for the browser.
- **What a server does.** It builds pages on demand, remembers and stores data, pulls from databases, and talks to outside services. Any page that knows your name is using a server.
- **Five building blocks chatbots can't give you on their own:** authentication (logging in), registration (signing up), databases, file storage, and server functions.
- **APIs.** An API is like a travel agent: your app asks it, and it checks the right service (payments, maps, AI) and brings back the answer.
- **Plan vs Build in Lovable.** Plan mode talks through the approach without writing code. Build mode writes code and costs more credits. Plan first in a free chatbot, then build.
- **Databases and logins from a prompt.** "Add user login with email and password" can create the full sign-up flow and the database tables. Row Level Security is the setting that keeps each user's data private.
- **Publish and own your code.** Lovable publishes to a live URL in one click and can sync your code to GitHub, so you're never locked in.
- **Never paste secret keys into a chat.** Payment and API keys go in the tool's dedicated key settings, not in your prompts.

## Files in this folder

| File | What it is |
| --- | --- |
| [prompts.md](prompts.md) | Lovable build prompts, the retest prompt and the build outline prompt |
| [user-test-prompt.md](user-test-prompt.md) | The TECH 36 User Test Prompt used in step 5 |
| [user-test-prompt-original.md](user-test-prompt-original.md) | An earlier, more detailed user test prompt with a scorecard (optional extra) |
| [user-test skill](https://github.com/planetoftheweb/vibe-coding-skills/tree/main/skills/user-test) | The same tool as an installable skill for Claude or ChatGPT |

---

## Assignment 3: The App Development Spectrum

**Tools:** [Lovable](https://lovable.dev) (building) · Any chatbot (planning) · Any image generator (assets)

Use a chatbot like Gemini or ChatGPT to plan your project first, then build it in Lovable. Your site needs a working form that saves to a database, user registration and login, and a published URL.

> **The point of this assignment:** cross the wall from a chatbot demo into a real app. Real apps *remember things* and *decide who sees what*. The thing to actually pull off: data a visitor enters saves and comes back later, and logging in unlocks something a visitor can't see. If you can explain what your server is doing for you, you've got it.

> **How to submit:** Answer the questions below. There is a **separate box for each item**:
>
> 1. Your VibeIt link (publish your site to VibeIt, then submit that link)
> 2. Your build outline
> 3. Your reflection (about 500 characters)
> 4. Your user test results
> 5. The 2 or more problems you fixed and what the retest showed

> **Test your link before you submit.** Open your published VibeIt link in a private or incognito window. If it doesn’t load there, it won’t load for me. A broken link is the most common reason work doesn’t count.

> **One project or four, your call.** You can grow one project across the course or build a separate one for each assignment. Both are fine. Do whatever keeps you motivated.

---

### 1. Plan Your Project

Before you spend Lovable credits, plan your project in a free chatbot. Describe what you want to build and ask it to help you think through the pages, the data you'll store, and what logged-in users should be able to do. Even better, bring your [MVPunk](https://mvpunk.com) MVP from Week 2 (your plan plus the agent, design, and project files) and hand it to Lovable as your starting context. Come to Lovable with a plan, not a blank slate.

---

### 2. Prepare Your Content

Use a chatbot to generate sample content for your site: placeholder text, bios, descriptions, feature lists, whatever your pages need. Don't waste Lovable credits writing copy.

For images, use Gemini's Nano Banana Pro or another image generator to create any visuals you want on your site: hero images, logos, icons, backgrounds. Have these ready before you start building.

---

### 3. Build It in Lovable

Go to [lovable.dev](https://lovable.dev) and start a new project. You can start from one of Lovable's project templates if one fits what you're building, or start from scratch. Paste your plan and content to get going.

> **All prompts below are suggestions.** Modify them, skip them, or write your own from scratch.

```text
Build me a [describe your site] with a clean, modern design. Include a landing page with a clear description of what the site does, a navigation bar, and a form where visitors can [describe what the form collects]. Make it responsive for mobile.
```

```text
Create a database table to store form submissions with columns for [list your fields]. When someone fills out the form, save their submission to the database. Show a confirmation message after successful submission.
```

```text
Add user registration and login. Create a sign-up page with email and password, a login page, and a way to log out. After logging in, redirect users to [a dashboard, their profile, the main page]. Show different content for logged-in users vs. visitors.
```

```text
Create a page that displays all form submissions from the database in a clean list or card layout. Add sorting or filtering. If users are logged in, let them see their own submissions separately.
```

---

### 4. Publish It

Click the **Share** or **Publish** button in Lovable. It will deploy your site and generate a public URL. **Test your live site** before submitting: try creating an account, logging in, submitting the form, and viewing the data. Then add the site to [VibeIt](https://vibeit.work) (public or private, your choice) and submit your VibeIt link.

> Test your published site before submitting. The Lovable preview and the deployed site can behave differently. Check the form, login flow, and any pages that pull data from the database.

---

### 5. User Test Your Live Site

You've looked at your site too many times to see it like a stranger. An AI can.

1. Paste the [User Test Prompt](https://gist.github.com/planetoftheweb/c277a17dacf5e45687a328a794d43a1e) into an AI. One that can open websites works best (Claude in Chrome or ChatGPT agent mode). If yours can't, the prompt tells you what to give it instead.
2. Answer its questions, starting with your live site link.
3. Review what it found and copy the full results. You'll paste them into your submission.
4. Pick at least 2 problems to fix, or fix them all. Fix them however you like. The prompt can also write an optional fix prompt for your AI agent, but that can use a lot of credits.
5. Publish again, then send this in the same chat and copy what it says:

```text
I made the changes. Test the site again and tell me what got better and what still needs work.
```

> **Test the live site.** Give it your published URL, not the Lovable preview. Never give the AI your real password.

---

### 6. Generate a Build Outline

Paste this into Lovable's chat in the same project where you built your site:

```text
Review our conversation and create a short outline of what we built together. No more than 10 bullet points, each under 150 characters. Focus on what was built or changed, not the prompts I typed.
```

Copy the result and paste it into your Canvas submission.

---

### 7. Write a Short Reflection

500 characters or less. What does your app remember, and who can see what? How was building with Lovable different from a chatbot, and did you hit any walls? Keep it casual.

---

### Checklist

|  |  |
| --- | --- |
| ☐ | Plan your project in a chatbot first |
| ☐ | Generate sample content and images before opening Lovable |
| ☐ | Build the site with pages, navigation, and a form |
| ☐ | Connect a database and make the form save data |
| ☐ | Add user registration and login |
| ☐ | Publish your site, test the live URL, and add it to VibeIt (public or private) |
| ☐ | Generate your build outline |
| ☐ | Write your short reflection |
| ☐ | Run the user test on your live site (phone and desktop) |
| ☐ | Fix at least 2 problems, publish again, and run the retest |
| ☐ | **Submit:** your VibeIt link, build outline, reflection, user test results, and your fixes plus retest |

---

### Completion

No grades. The certificate is based on attending the sessions; assignments should be submitted and up to date too.

---

### Tips

* **Plan outside Lovable.** Chatbots are free. Use them for brainstorming, your MVP, and content. Save your Lovable credits for actual building.
* **Start from a template.** Lovable's project templates give you a head start. Pick one close to what you're building and customize from there.
* **Describe problems clearly.** "The form submits but nothing shows up in the database" is debuggable. "It's broken" is not.
* **Test the published site.** The preview and the deployed version can behave differently. Always check the live URL.
* **Questions?** Send me a message in Canvas Inbox. Submit your work through this assignment, not by email, so it's recorded with your submission.

---

## Sources

- Assignment 3 description from the course site (Canvas), converted to markdown.
- Week overview and key ideas: rewritten for beginners from the class slides, Part 3: The App Development Spectrum.
- Gist: [TECH 36 User Test Prompt](https://gist.github.com/planetoftheweb/c277a17dacf5e45687a328a794d43a1e), copied into [user-test-prompt.md](user-test-prompt.md).
- Gist: [User Test](https://gist.github.com/planetoftheweb/93aaad59ea1f6bb5510917e046ef7618), copied into [user-test-prompt-original.md](user-test-prompt-original.md).

[Back to the main index](../README.md)
