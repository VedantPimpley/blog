---
name: publish
description: Publish the blog — commit, push, and confirm GitHub Pages rebuilt. Use when the user says publish, push the blog, put the post live, or asks whether the site is live yet.
---

# Publish the blog

Run the repo's script from the blog root. It does everything; do not hand-roll
the git and polling steps.

```bash
./publish                  # commit everything, push, wait for the build
./publish -m "message"     # with a specific commit message
./publish --check          # lint only — no commit, no push
```

The script lints changed posts, commits, pushes to `main`, then waits for
GitHub Pages to finish building **that exact commit** and checks the site
returns 200. A build takes 40-90s.

## Before running

Show the user `git diff` and mention anything that changes a published URL —
a renamed post file 404s its old links. Never reword the user's prose; a
markdown mechanics fix (such as a missing blank line before a paragraph that
follows a list) is fine, but say that you made it.

## If it fails

- `no front matter` — the post must start with a line of exactly `---`.
- `build failed:` — the message comes from Jekyll; it is usually invalid YAML
  in a post's front matter. Fix and run again.
- Timed out — check https://github.com/VedantPimpley/blog/deployments.
