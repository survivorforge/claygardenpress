# Clay Garden Press

Source for [claygardenpress.com](https://claygardenpress.com) — a small independent publication.

## Stack

- **Eleventy** (v3) — static site generator
- **Cloudflare Pages** — hosting, automatic deploy on `git push` to `main`
- Markdown content + Nunjucks templates

## Local development

```bash
npm install
npm run dev      # serve on http://localhost:8080 with live reload
npm run build    # build to _site/
```

## Structure

```
src/
├── _includes/layouts/    # base + post templates
├── posts/                # markdown content (one file per post)
├── static/               # CSS, images, fonts
├── index.njk             # homepage
├── about.njk
├── privacy.njk
├── sitemap.njk           # → /sitemap.xml
├── feed.njk              # → /feed.xml
└── robots.txt
```

## Publishing a post

Add a markdown file to `src/posts/<slug>.md` with frontmatter:

```yaml
---
layout: layouts/post.njk
title: Your title
description: One-sentence summary for SEO + RSS
date: 2026-05-18
tags: [topic]
---

Your post body in markdown.
```

Then `git push` to `main`. Cloudflare Pages deploys automatically.
