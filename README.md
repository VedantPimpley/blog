# Blog

Minimalist blog, Jekyll on GitHub Pages.

## New post

Create `_posts/YYYY-MM-DD-slug.md`:

```markdown
---
layout: post
title: "Your Title"
description: "One line for search results and link previews."
---

Your text, in Markdown.
```

Commit and push — GitHub Pages rebuilds in about a minute.

## Local preview

```bash
bundle install          # once
bundle exec jekyll serve # http://localhost:4000
```

## Layout

- `_layouts/` — HTML templates (`default`, `post`, `page`)
- `assets/style.css` — all styling, light + dark
- `index.html` — the essay list
- `about.md` — the about page
