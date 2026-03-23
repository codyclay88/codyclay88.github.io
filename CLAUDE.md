# CLAUDE.md

This file provides context for AI assistants working in this repository.

## Overview

This is a personal Jekyll-based static website for Cody Clay, hosted on GitHub Pages at [codyclay.com](https://codyclay.com). The site serves as a personal journal and blog.

## Technology Stack

- **Static site generator**: Jekyll 4.4.1
- **Theme**: minima (~2.5)
- **Plugin**: jekyll-feed (~0.12)
- **Hosting**: GitHub Pages (custom domain via `CNAME`)
- **Dependency manager**: Bundler (Ruby gems)

## Repository Structure

```
.
├── _config.yml          # Jekyll site configuration (title, URL, theme, plugins)
├── _posts/              # Blog posts as Markdown files
│   ├── YYYY-MM-DD-title.markdown
│   └── ...
├── 404.html             # Custom 404 error page
├── CNAME                # Custom domain: codyclay.com
├── Gemfile              # Ruby gem dependencies
├── Gemfile.lock         # Locked gem versions
├── index.markdown       # Homepage content (layout: home)
└── styles.css           # Custom CSS overrides
```

## Content Conventions

### Blog Posts

Posts live in `_posts/` and follow Jekyll's naming convention:

```
YYYY-MM-DD-slug.markdown
```

Each post requires front matter at the top:

```yaml
---
layout: post
title: "Your Post Title"
---
```

Post content uses standard Markdown. The existing posts follow a journal-entry format with:
- An optional opening quote block (`> quote`)
- A `## To-Dos` section with checkboxes
- A `## Thoughts` section with `###` subsections for individual topics

### Homepage

`index.markdown` uses `layout: home`, which renders the Jekyll minima home layout (lists recent posts automatically).

### 404 Page

`404.html` uses `layout: page` with `permalink: /404.html`.

## Development Workflow

### Local Setup

```bash
bundle install
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`.

**Note**: `_config.yml` is not hot-reloaded. Restart `jekyll serve` after any changes to that file.

### Adding a New Post

1. Create a file in `_posts/` named `YYYY-MM-DD-descriptive-slug.markdown`
2. Add the required front matter (`layout: post`, `title:`)
3. Write content in Markdown

### Deployment

Pushing to the `main` branch on GitHub triggers automatic deployment via GitHub Pages. No build pipeline or CI configuration is needed beyond what GitHub Pages provides natively.

## Site Configuration

Key values in `_config.yml`:

| Setting | Value |
|---|---|
| `title` | Cody Clay's Website |
| `email` | codyclay88@gmail.com |
| `url` | https://codyclay.com |
| `baseurl` | (empty) |
| `theme` | minima |
| `github_username` | codyclay88 |

## Key Conventions for AI Assistants

- **Do not alter personal journal content** — the posts in `_posts/` are personal reflections; treat them as read-only unless explicitly asked to edit them.
- **Do not change `_config.yml` site identity fields** (title, email, url) without explicit instruction.
- **Keep it simple** — this is a minimal personal blog. Avoid over-engineering with complex layouts, JavaScript frameworks, or unnecessary plugins.
- **Preserve the minima theme** unless a theme change is explicitly requested.
- **Post file names must match the date pattern** `YYYY-MM-DD-slug.markdown` — Jekyll will not render posts that don't follow this convention.
- **Front matter is required** on every post and page — missing front matter causes Jekyll to treat the file as a static asset, not a page.
- **Custom styles** go in `styles.css` — the file currently exists but is empty, ready for overrides to the minima theme.
