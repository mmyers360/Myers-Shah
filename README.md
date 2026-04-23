# Myers & Shah Blog — Hugo Setup

## What This Is

A Hugo-powered blog for the Myers & Shah website, designed to match your v4 rebrand (Fraunces, Space Grotesk, navy/gold palette). Blog posts live at `/insights/[post-slug]/` on your site.

## Quick Start

### 1. Install Hugo

**Mac (Homebrew):**
```bash
brew install hugo
```

**Windows (Chocolatey):**
```bash
choco install hugo-extended
```

**Windows (Scoop):**
```bash
scoop install hugo-extended
```

Or download directly from https://github.com/gohugoio/hugo/releases

### 2. Preview Locally

```bash
cd myers-shah-blog
hugo server -D
```

Open http://localhost:1313/posts/ to see the blog listing.

### 3. Build for Production

```bash
hugo
```

This generates all HTML files into the `public/` directory.

## Writing a New Post

Create a new Markdown file in `content/posts/`:

```bash
hugo new posts/my-new-post-title.md
```

Or manually create a file like `content/posts/my-post.md`:

```markdown
---
title: "Your Post Title"
date: 2026-05-01
draft: false
author: "Mel E. Myers, Esq."
category: "Zoning"
summary: "A one-sentence summary for the listing page."
tags: ["zoning", "DC", "variance"]
---

Your post content goes here. Use standard Markdown:

## Subheading

Regular paragraphs, **bold**, *italic*, [links](https://example.com).

- Bullet points
- Work fine

> Blockquotes too.
```

### Front Matter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | Post headline |
| `date` | Yes | Publication date (YYYY-MM-DD) |
| `draft` | Yes | Set `false` to publish, `true` to hide |
| `author` | No | Defaults to template value |
| `category` | No | Shown as a label (e.g., "Zoning", "Entitlements", "Tax Incentives") |
| `summary` | No | 1-2 sentence description for the listing page |
| `tags` | No | Array of tags shown at bottom of post |

## Deploying to Netlify

### Option A: Integrate Into Your Existing Site Repo

If your current site repo is static HTML files:

1. Copy this entire `myers-shah-blog` folder into your repo (or merge its contents)
2. In Netlify site settings → Build & Deploy:
   - **Build command:** `hugo`
   - **Publish directory:** `public`
   - **Hugo version:** Set environment variable `HUGO_VERSION` = `0.147.0`
3. Copy your existing static HTML pages (index.html, practice-areas.html, etc.) into the `static/` folder — Hugo will include them as-is in the build output
4. Push to GitHub — Netlify auto-builds

### Option B: Separate Blog Repo (Simpler Start)

1. Create a new GitHub repo for the blog
2. Push this folder to it
3. Create a new Netlify site pointed at that repo
4. Configure build command: `hugo`
5. Configure publish directory: `public`
6. Set up the site at a path or subdomain

### Netlify Build Settings

In your Netlify dashboard under Site Settings → Build & Deploy:

```
Build command:       hugo
Publish directory:   public
```

Under Environment Variables, add:
```
HUGO_VERSION = 0.147.0
```

## Integrating With Your Existing Static Site

The cleanest approach: move your existing HTML files into this Hugo project's `static/` folder. Hugo copies everything in `static/` directly to the output. So:

```
static/
  index.html              ← your existing homepage
  practice-areas.html     ← existing page
  attorneys.html          ← existing page
  zoning-and-entitlements.html
  development-incentives.html
  land-use-litigation.html
  commercial-leasing.html
  images/
    hero-1.jpg
    hero-2.jpg
    ...
  css/
    main.css              ← blog CSS (already here)
```

Hugo will generate the blog pages alongside your static pages. The nav links in the blog templates already point to your existing page URLs.

## Project Structure

```
myers-shah-blog/
├── hugo.toml                  # Site config (firm info, nav, URLs)
├── archetypes/
│   └── default.md             # Template for new posts
├── content/
│   └── posts/
│       ├── _index.md          # Section config
│       └── *.md               # Your blog posts
├── layouts/
│   ├── _default/
│   │   ├── baseof.html        # Base HTML wrapper
│   │   ├── list.html          # Blog listing page
│   │   └── single.html        # Individual post page
│   └── partials/
│       ├── nav.html           # Site navigation
│       └── footer.html        # Site footer
└── static/
    └── css/
        └── main.css           # All styles
```

## SEO Notes

- Each post generates clean URLs at `/insights/[slug]/`
- Open Graph meta tags are included for social sharing
- The `summary` field populates the meta description
- Post titles become the page `<title>` tag
- Sitemap is auto-generated at `/sitemap.xml`

## Suggested Post Cadence

2-4 posts per month targeting search queries like:
- "zoning variance attorney DC"
- "land use lawyer Virginia"
- "how to appeal zoning denial"
- "DC tax incentives real estate"
- "site plan approval Northern Virginia"
- "commercial lease review DC"
