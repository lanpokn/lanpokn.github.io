# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic homepage for Haiqian Han, a Master's student at Tsinghua University researching computer vision and event-based cameras.

**Live Site**: https://lanpokn.github.io/
**Tech Stack**: Jekyll, GitHub Pages, Academic Pages template

---

## Local Development

```bash
# Install dependencies
bundle install

# Serve locally with live reload (uses hawkins gem)
bundle exec jekyll liveserve

# Or standard serve
bundle exec jekyll serve

# Build only
bundle exec jekyll build
```

Site runs at `http://localhost:4000` by default.

---

## Design Philosophy

**Single Entry Point**: This site is intentionally minimal with only one main page. All navigation links except the homepage have been disabled.

**Key Constraint**: DO NOT create multi-page structures. The entire content should be on the homepage (`_pages/about.md`).

---

## Key Configuration

### 1. Collections Disabled (`_config.yml:211-223`)
All Jekyll collections have `output: false` to prevent generating individual pages:
- teaching, publications, portfolio, talks

### 2. Navigation Stripped (`_data/navigation.yml`)
All navigation links are commented out. Only the homepage is accessible.

### 3. SEO Modifications (`_includes/seo.html:140-142`)
Added robots meta tag to discourage Google from showing sitelinks in search results.

---

## Homepage Structure (`_pages/about.md`)

Sections in order:
1. **Brief intro** - Current position, research focus, Ph.D. seeking status
2. **Education** - Degree, institution, years (reverse chronological)
3. **Publications** - Separated into "First Author" and "Co-authored"
4. **Experience** - Internships (reverse chronological)

Publication format:
```markdown
Author names. **Paper Title**. *Conference/Journal Name*, Year: Pages.
```

Contact info lives in two places: `_pages/about.md` (email line) and `_config.yml` (author section).

---

## Deleted Pages

**DO NOT recreate these pages**:
- `/cv/` - Intentionally deleted (commit 075152b).

---

## DO NOT

1. ❌ Create new pages in `_pages/`
2. ❌ Enable collections output in `_config.yml`
3. ❌ Uncomment navigation links in `_data/navigation.yml`
4. ❌ Recreate the CV page
5. ❌ Add verbose descriptions or template boilerplate

---

## Site Deployment

Push to `master` branch → GitHub Pages automatically builds and deploys (~2 minutes).

**Expected**: Google may show outdated links (CV, collections) for 1-4 weeks after deletion. Wait for natural re-indexing, or use Google Search Console to request removal.
