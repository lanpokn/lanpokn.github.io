# AGENTS.md

Guidance for Codex and other coding agents working in this repository.

## Project Overview

This repository contains Haiqian Han's personal academic homepage:

- Live site: https://lanpokn.github.io/
- Stack: Jekyll, GitHub Pages, Academic Pages template
- Primary purpose: a minimal single-page academic profile for research, education, publications, experience, and contact information.

The site has been intentionally simplified from the Academic Pages template. Treat the current minimal shape as a product decision, not unfinished work.

## Core Site Constraint

This is a single-entry homepage site. The live root page `/` is currently served by
the static `index.html` in the repository root. Do not assume that changing
`_pages/about.md` changes the live homepage: `_pages/about.md` is a legacy/alternate
Jekyll page in the current repository, while `index.html` is the actual deployed
entry point.

Keep the complete homepage content in the active entry point. When changing profile
or publication information, inspect and update `index.html` first, then check
`_pages/about.md` for stale duplicate content so the two files do not contradict
each other.

Do not create or restore multi-page structures unless the user explicitly asks to reverse the current site direction. In particular:

- Do not add new public pages under `_pages/`.
- Do not recreate the deleted `/cv/` page.
- Do not enable collection output in `_config.yml`.
- Do not uncomment navigation links in `_data/navigation.yml`.
- Do not add Academic Pages sample/template boilerplate back into the user-facing site.

## Key Files

- `index.html`: current live homepage and primary source for the rendered `/` page.
- `_pages/about.md`: legacy/alternate Jekyll homepage content; keep it consistent
  with `index.html` when the same profile or publication information appears there.
- `_config.yml`: site-wide Jekyll config and author metadata.
- `_data/navigation.yml`: header navigation, intentionally stripped/commented.
- `_includes/seo.html`: includes a robots meta change intended to reduce search sitelinks.
- `CLAUDE.md`: prior agent guidance and historical context.
- `README.md`: upstream Academic Pages documentation; useful for generic Jekyll setup, but not authoritative for this site's simplified design.

Contact information appears in both `_pages/about.md` and the author section of `_config.yml`; keep them consistent when editing contact details.

## Required Profile Information

Do not remove or silently replace the following important facts when simplifying or
rewriting the homepage:

- Ph.D. student in Computer Science at Northwestern University, advised by Prof.
  Emma Alexander.
- M.Eng. in Control Science and Engineering at Tsinghua University, supervised by
  Prof. Xiangyang Ji.
- B.Eng. from Zhejiang University.
- Research interests in bio-inspired vision/cameras, computational imaging,
  simulation, and computer vision.
- Current contact email: `haiqianhan2031@u.northwestern.edu`.

Preserve the education, publication, research, internship, teaching, awards, and
skills sections already present in `index.html` unless the user explicitly asks to
remove or replace them. In particular, do not replace the full CV-style homepage
with the shorter `_pages/about.md` content merely to simplify the site.

## Homepage Content Pattern

Maintain the current concise academic CV style. The homepage sections in `index.html`
are ordered as:

1. Profile/About and research interests
2. Education
3. Publications
4. Internship Experience
5. Teaching Assistant
6. Awards & Achievements
7. Skills

Preserve this full CV-style structure unless the user explicitly requests a
different homepage design.

Use reverse chronological ordering for education and experience.

Publication entries use this format:

```markdown
Author names. **Paper Title**. *Conference/Journal Name*, Year: Pages.
```

Keep descriptions factual and compact. Avoid verbose personal-site copy, marketing language, and restored template examples.

## Local Development

Install Ruby dependencies:

```bash
bundle install
```

Serve locally with live reload:

```bash
bundle exec jekyll liveserve
```

Standard local serve:

```bash
bundle exec jekyll serve
```

Build only:

```bash
bundle exec jekyll build
```

The local site normally runs at `http://localhost:4000`.

For JavaScript asset changes, this repo also has npm scripts:

```bash
npm run build:js
```

Only run npm asset builds when changing relevant JavaScript files.

## Validation

For content-only changes, inspect the rendered Markdown and run a Jekyll build when practical:

```bash
bundle exec jekyll build
```

For layout, include, Sass, config, or navigation changes, prefer a local Jekyll build before finishing. If dependencies are missing and installing them is outside the current task, report that validation could not be run.

## Editing Rules

- Keep edits narrowly scoped to the user request.
- Preserve the single-page architecture by default.
- Prefer existing Jekyll, Liquid, Sass, and Academic Pages patterns over new abstractions.
- Avoid touching generated or vendored template files unless the requested change requires it.
- Do not revert unrelated user changes in the working tree.
- Use clear, minimal Markdown for profile content.
- Preserve front matter in Jekyll pages.
- Use relative paths and existing asset directories (`images/`, `files/`, `assets/`) consistently.

## Deployment

Deployment is handled by GitHub Pages from the `master` branch after push. Builds usually complete within a few minutes.

Outdated Google search links, especially removed CV or collection pages, may persist for weeks after deletion. The intended fix is re-indexing or removal through Google Search Console, not restoring those pages.
