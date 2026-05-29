# Personal blog (Jekyll + GitHub Pages)

A minimal blog in the style of karpathy.github.io: a dated list of posts on the
homepage, clean post pages, with LaTeX math and code highlighting built in.

## Quick start (deploy in 2 minutes)

This is a **user site** (served at `https://<username>.github.io`):

1. Create a repo named exactly `<username>.github.io` (for you: `lightingooo.github.io`).
2. Copy all these files into it.
3. Edit `_config.yml` — set `title`, `email`, `github_username`, `url`.
4. Commit and push to the `main` branch.
5. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   pick `main` / `(root)`. Wait ~1 minute; your site is live.

No plugins, no Actions needed — GitHub builds the Jekyll site for you.

## Writing a post (bilingual)

Chinese is the primary language. For each post you upload **two files** to
`_posts/`, paired by a shared `ref` value.

Chinese version — `2026-06-01-my-post.md`:

```markdown
---
layout: post
title: "我的标题"
date: 2026-06-01
lang: zh
ref: my-post
description: "首页上显示的一句话摘要。"
---

正文，行内公式 \( a^2 + b^2 \)，整行公式：

$$ E = mc^2 $$
```

English version — `2026-06-01-my-post-en.md`:

```markdown
---
layout: post
title: "My title"
date: 2026-06-01
lang: en
ref: my-post
description: "One-line summary shown on the English homepage."
---

English content here.
```

Rules:
- `lang` must be `zh` or `en`.
- `ref` must be **identical** in both files — this is what links them.
- The Chinese homepage (`/`) lists `zh` posts; the English homepage (`/en/`) lists `en` posts.
- Each post page shows a `中文 · English` toggle. If you haven't made the
  translation yet, only the current language shows — no error.

## Run it locally (optional)

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```

## File map

- `_config.yml`     — site settings
- `index.html`      — homepage (post list)
- `about.md`        — about page
- `_layouts/`       — page templates
- `_posts/`         — your posts
- `assets/css/`     — the single stylesheet
- `feed.xml`        — RSS feed
