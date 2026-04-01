# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Hugo static site for the *Digital Old Norse Studies* research network, deployed to GitHub Pages via GitHub Actions on every push to `main`.

## Common commands

```bash
hugo server          # serve locally at http://localhost:1313 with live reload
hugo build           # build to ./public (used by CI)
```

To create a new post or page:
```bash
hugo new posts/my-post-title.md
hugo new pages/my-page.md
```

## Content structure

- `content/_index.md` — home page
- `content/pages/` — static pages (type: `"page"`)
- `content/posts/` — blog/news posts in chronological order (type: `"post"`)

Every content file needs frontmatter with `title`, `date`, `type`, and optionally `description`. The `type` field must be either `"page"` or `"post"` — this distinction is used by the Gokarna theme to control how content is displayed.

## Theme

Uses the [Gokarna](https://github.com/526avijitgupta/gokarna) theme as a git submodule at `themes/gokarna`. Local overrides live in `layouts/partials/`. After cloning, initialise with:

```bash
git submodule update --init --recursive
```

## Git workflow

- Never commit directly to `main`. Use a feature branch and open a PR.
- PRs require at least one review from another network member before merging.
- Merge using **squash merge** with a descriptive commit message.
- Branch naming: lowercase, hyphens, short, imperative (e.g. `add-annual-meeting-post`, `update-member-affiliations`). `wip/` prefix is fine.
