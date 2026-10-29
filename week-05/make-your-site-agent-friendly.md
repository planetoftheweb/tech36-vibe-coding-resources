# Make sure your site is agent friendly

When you share your link with ChatGPT, Claude, Perplexity or a search engine, you probably expect it to "see" your site the way you do. Often it doesn't. A lot of vibe-coded apps look great in a browser but show a crawler almost nothing. This lesson explains why, how to check in two minutes, and gives you a prompt that lets your coding agent audit and fix your own app.

You'll need a published site (VibeIt, Firebase Hosting, Netlify, Vercel or similar) and a coding harness (Claude Code, Cursor, or Codex). No harness? You can still run the checks yourself and paste the prompt at the end into any AI with your code.

## 1. Why AI assistants often can't read your site

Most apps built with AI tools are single-page apps (SPAs). The server sends a nearly empty page, and JavaScript builds everything you see after it loads. Your browser runs that JavaScript. Many crawlers and AI assistants **don't**. They download the HTML, read it, and move on.

Here's what they get from an empty SPA:

```html
<!doctype html>
<html>
  <head><title>My App</title></head>
  <body>
    <div id="root"></div>
    <script src="/assets/index-a1b2c3.js"></script>
  </body>
</html>
```

An empty `<div>` and a script. No words, no headings, no links. To that reader, your site is blank.

The fix is to make sure the **raw HTML** already contains your real content, and to give crawlers a few well-known files that tell them where things are. None of this changes how your site looks to people.

## 2. Check what a crawler sees

Two ways, pick either.

**In your browser:** open your site, right-click, choose **View Page Source** (or put `view-source:` in front of the address, like `view-source:https://yoursite.com`). This is the raw HTML before JavaScript runs. Don't use Inspect, because that shows the page after JavaScript has changed it. Do you see your real text in the source? If you only see an empty `<div id="root">` and script tags, crawlers see a blank page.

**With curl** (a command that downloads a page like a crawler would, with no JavaScript):

```bash
curl -s https://yoursite.com/ | head -50
```

Want a rough count of the readable text? This strips script and style blocks and tags, then counts characters:

```bash
curl -s https://yoursite.com/ | perl -0pe 's/<script.*?<\/script>//gs; s/<style.*?<\/style>//gs; s/<[^>]+>//g; s/\s+/ /g' | wc -c
```

A few hundred characters or more of real words is a good sign. Close to zero means crawlers can't read your page.

## 3. Put real text in the HTML

Pick whichever fits how your app is built:

- **Prerendering.** A build step runs your app ahead of time and saves the finished HTML for each page. Visitors and crawlers both get real content right away, and your app still takes over in the browser. Ask your agent to set this up for your framework.
- **Static HTML.** If your site doesn't change much, plain HTML files with your content in them are the simplest and most crawler-friendly option.
- **A basic fallback.** At minimum, put a real heading and a few sentences about what your site does inside the page, so even an empty-looking app says something.

Every page also needs a **title** and a **meta description** in the `<head>`. This is the short summary search results and AI tools use:

```html
<head>
  <title>Pet Tracker: keep every pet's vet visits in one place</title>
  <meta name="description" content="Pet Tracker is a free app that stores vaccine dates, vet visits and medicine reminders for all your pets." />
  <link rel="canonical" href="https://yoursite.com/" />
</head>
```

Write a description of about 120 to 160 characters that says what the page is, in plain words.

## 4. robots.txt with a Sitemap line

`robots.txt` sits at the top of your site (`https://yoursite.com/robots.txt`) and tells crawlers what they may read. Put the file in the folder your host publishes (usually `public/`):

```text
User-agent: *
Allow: /

Sitemap: https://yoursite.com/sitemap.xml
```

The `Sitemap:` line is the important part. It points crawlers to a full list of your pages. Use your real domain, with `https://`.

Keep private pages out with `Disallow`, for example `Disallow: /admin`. Remember that `robots.txt` is public and only a polite request. It never protects anything secret. Real protection comes from logins and security rules.

## 5. sitemap.xml

A sitemap is a list of every page you want found. Put it at `https://yoursite.com/sitemap.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url><loc>https://yoursite.com/</loc></url>
  <url><loc>https://yoursite.com/about</loc></url>
  <url><loc>https://yoursite.com/privacy</loc></url>
</urlset>
```

List real pages only, and make sure each one loads. If your app has many pages (one per product, post or profile), have your build step generate the sitemap from your data, so it never goes stale.

## 6. An RSS or Atom feed, plus a link to it

If your site publishes things over time (posts, products, results, updates), a feed gives readers and AI tools a clean, structured list of what's new. Create `/feed.xml` (RSS) or `/atom.xml`. Then add this line inside the `<head>` of your pages so tools can discover it:

```html
<link rel="alternate" type="application/rss+xml" title="My Site feed" href="/feed.xml" />
```

For Atom, use `type="application/atom+xml"`. No articles or updates on your site? Skip this one. It's nice to have, not a must.

## 7. llms.txt and AGENTS.md

These two files are friendly notes for AI tools. They're plain text and easy to add.

- **`/llms.txt`** is a short summary of your site for language models: what it is, who made it, and links to your key pages and data. Think of it as a table of contents written for an AI.
- **`/AGENTS.md`** is a short set of rules for AI agents that use your site or data. For example: "cite the page you got a number from" or "never invent values that aren't published."

A tiny `llms.txt` looks like this:

```markdown
# Pet Tracker

> A free app for keeping every pet's vet visits and vaccine dates in one place.

Site: https://yoursite.com

## Key pages

- https://yoursite.com/        Home
- https://yoursite.com/about   What the app does and who made it
- https://yoursite.com/privacy Privacy policy
```

These aren't official web standards that every crawler reads yet, but they cost almost nothing and some AI tools look for them. (Your repo's own `AGENTS.md`, from Week 2, is a different file with the same name. It tells your coding agent how to build. This one is published on your live site for visitors' agents.)

## 8. Real 404s, not "200 for everything"

This one catches a lot of SPAs. Many setups use a catch-all rule that sends **every** unknown address to `index.html`. It's handy for routing, but it means a made-up address like `/this-page-does-not-exist` answers **200 OK** with your home page. Crawlers see endless duplicate pages, and broken links never look broken.

A missing page should return status **404**. Check:

```bash
curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/this-page-does-not-exist-12345
```

You want `404`. If you see `200`, you have a catch-all.

**On Firebase Hosting**, look in `firebase.json` for a rewrite like this:

```json
"rewrites": [{ "source": "**", "destination": "/index.html" }]
```

That's what returns 200 for everything. The fix has two parts:

1. Give every real page its own file (prerendering does this), or list your real routes in `rewrites` one by one instead of `**`.
2. Add a `404.html` to your published folder. Firebase Hosting serves it, with a real 404 status, for any address that doesn't match.

Other static hosts have the same idea: Netlify and Cloudflare Pages also serve a `404.html`, and Vercel has its own 404 setup. Ask your agent for the right setting on your host. Your 404 page can still use your site's look and have a link back to the home page.

## 9. Don't block the AI crawlers by accident

Some templates and "SEO" tips copy-paste lines like these into `robots.txt`:

```text
User-agent: GPTBot
Disallow: /

User-agent: ClaudeBot
Disallow: /
```

Those lines tell OpenAI's and Anthropic's crawlers to stay out. If you want your site to show up when people ask an AI assistant about you, remove them. If you blocked them on purpose, for example to keep your writing out of AI training, that's a fine choice. The goal is that it's **your decision**, not an accident. Also check that your host or a security setting (like a bot-blocking firewall rule) isn't quietly refusing these visitors.

## Verification checklist

Replace `https://yoursite.com` with your real address. Run each command and compare with what you want.

| Check | Command | You want |
| --- | --- | --- |
| Real text in the HTML | `curl -s https://yoursite.com/ \| grep -i "<h1"` | Your real heading appears |
| Meta description | `curl -s https://yoursite.com/ \| grep -i 'name="description"'` | A line with a real summary |
| robots.txt exists | `curl -s https://yoursite.com/robots.txt` | Text with a `Sitemap:` line |
| Sitemap works | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/sitemap.xml` | `200` |
| Sitemap is XML | `curl -s https://yoursite.com/sitemap.xml \| head -5` | Starts with `<?xml` and `<urlset` |
| Feed (if you have one) | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/feed.xml` | `200` |
| Feed is linked | `curl -s https://yoursite.com/ \| grep -i 'rel="alternate"'` | A `<link rel="alternate">` line |
| llms.txt | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/llms.txt` | `200` |
| AGENTS.md | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/AGENTS.md` | `200` |
| Real 404 | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/no-such-page-12345` | `404` |
| Not blocking AI bots | `curl -s https://yoursite.com/robots.txt \| grep -i -E "GPTBot\|ClaudeBot"` | Nothing, unless you blocked them on purpose |
| Real pages still load | `curl -s -o /dev/null -w "%{http_code}\n" https://yoursite.com/about` | `200` for each real page |

Then open your site in a normal browser and make sure it still looks and works the way it did before.

## Checklist

|  |  |
| --- | --- |
| ☐ | View Page Source or curl shows your real text, not an empty `<div>` |
| ☐ | Every page has a title and a meta description |
| ☐ | `robots.txt` exists and has a `Sitemap:` line |
| ☐ | `sitemap.xml` returns 200 and lists real pages |
| ☐ | A feed exists and is linked with `rel="alternate"` (or you have no articles, so you skipped it) |
| ☐ | `llms.txt` and `AGENTS.md` are published |
| ☐ | An unknown address returns 404, not 200 |
| ☐ | GPTBot and ClaudeBot aren't blocked unless you meant to |
| ☐ | The site still looks and works the same for people |

## Prompt for your AI coding tool

Paste this into Claude Code, Cursor, or Codex inside your project. Replace the address in `[square brackets]` with your own.

```text
Audit and fix my site so crawlers and AI assistants that don't run JavaScript can read it. Don't change how the site looks or works for people, and don't print any secret values.

My live URL: [https://yoursite.com]
My host: [Firebase Hosting, or Netlify, Vercel, Cloudflare Pages, GitHub Pages, other]

Step 1, audit (change nothing yet):
Run these against my live URL and report what you find:
- curl -s [URL]/ : does the raw HTML contain real visible text (more than about 200 characters outside script tags), an h1, a title and a meta description? Or is it just an empty root div plus scripts?
- curl -s [URL]/robots.txt : does it exist, and does it have a "Sitemap:" line? Does it block GPTBot or ClaudeBot?
- curl -s -i [URL]/sitemap.xml : status 200 and valid XML?
- Is there a feed (/feed.xml, /rss.xml or /atom.xml) and a <link rel="alternate"> to it in the HTML? (Only needed if my site publishes articles or updates.)
- /llms.txt and /AGENTS.md : do they exist?
- curl -s -o /dev/null -w "%{http_code}" [URL]/no-such-page-12345 : does it return 404, or 200?
Then read my code and config (for Firebase Hosting that means firebase.json, especially "rewrites", plus my build setup) and tell me the cause of each problem. Give me a short plan, smallest changes first, and wait for my OK.

Step 2, fix (after I approve):
1. Real content in the HTML. Choose the simplest option for my framework: prerender every public page at build time, or write static HTML. The app must still take over in the browser. Add a unique title, meta description and canonical link to each page.
2. Add robots.txt with "User-agent: *", "Allow: /", a Disallow for private areas like /admin, and a "Sitemap: [URL]/sitemap.xml" line. Do not block GPTBot or ClaudeBot unless I tell you to.
3. Generate sitemap.xml at build time from my real pages. Use my real domain with https. No private or admin pages.
4. If my site has articles, posts or other updates, generate /feed.xml (RSS 2.0) and add <link rel="alternate" type="application/rss+xml" href="/feed.xml"> to the head of my pages. If it doesn't, skip this and say so.
5. Add llms.txt (what the site is, who made it, links to key pages and any data) and an AGENTS.md of rules for AI agents that use my site (cite sources, never invent data). Publish both at the site root.
6. Fix 404s. For Firebase Hosting: remove the catch-all rewrite ("**" to /index.html) if every real page now has its own file, or replace it with rewrites for only my real routes. Add a 404.html to the public folder so unknown addresses get a real 404 status. For other static hosts, use that host's way to serve a 404 page with a 404 status. My real pages and deep links must keep working.
7. Don't add secrets, env files or anything private to any public file.

Step 3, verify:
Build, then test locally or on a preview channel before touching my live site (on Firebase Hosting, use "firebase hosting:channel:deploy" for a preview). Re-run every curl check from Step 1 against the preview and show me a table of results: check, command, result, pass or fail. Confirm real pages still return 200, an unknown page returns 404, and open the preview in a browser to check that the site looks and works as before. Show me the changes before you commit. Don't deploy to live until I say so.
```

> **Don't paste secret keys into an AI chat.** The audit only reads public pages and your site's config.

---

[Back to Week 5](README.md) · [Main index](../README.md)
