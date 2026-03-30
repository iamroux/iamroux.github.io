# Site

Personal writing site built with [Eleventy (11ty)](https://www.11ty.dev/).

## Setup

```
npm install
npm start        # local dev server at http://localhost:8080
npm run build    # production build to _site/
```

## Writing a new post

Create a markdown file in `src/notebook/` or `src/technical/`:

```markdown
---
layout: post.njk
title: "Your title here"
date: 2026-04-01
section: notebook
---

Your writing goes here. Standard markdown — **bold**, *italic*, [links](url), `code`, etc.
```

- `section` is either `notebook` or `technical`
- `date` determines sort order (newest first)
- File name becomes the URL slug: `my-post.md` → `/notebook/my-post/`
- Homepage shows the 10 most recent posts across both sections

## Project structure

```
src/
  _includes/       templates (base layout, post layout, section list)
  _data/site.json  site title
  css/style.css    all styles + dark mode + mobile
  index.njk        homepage
  about.md         about page
  contact.md       contact page
  notebook/        non-technical writing
  technical/       technical writing
.eleventy.js       eleventy config
.github/workflows/ github pages deploy
```

## Editing pages

- **Site title**: `src/_data/site.json`
- **Nav links**: `src/_includes/base.njk`
- **Homepage intro**: `src/index.njk`
- **Styles/theme**: `src/css/style.css` (light vars in `:root`, dark in `[data-theme="dark"]`)

## Deployment

Pushes to `main` auto-deploy via GitHub Actions. In your repo settings, set Pages source to "GitHub Actions".
