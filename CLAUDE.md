# Project Overview

Personal academic homepage for Haiqian Han, a Master's student at Tsinghua University researching computer vision and event-based cameras.

**Live Site**: https://lanpokn.github.io/
**Tech Stack**: Jekyll, GitHub Pages, Academic Pages template

---

## Design Philosophy

**Single Entry Point**: This site is intentionally minimal with only one main page. All navigation links except the homepage have been disabled.

**Key Constraint**: DO NOT create multi-page structures. The entire content should be on the homepage (`_pages/about.md`).

---

## Project Structure

```
├── _config.yml           # Site configuration
├── _data/
│   └── navigation.yml    # All navigation links are commented out
├── _pages/
│   └── about.md          # MAIN CONTENT (permalink: /)
├── _includes/
│   └── seo.html          # Modified to prevent Google sitelinks
├── _publications/        # Not displayed (collections disabled)
├── _talks/               # Not displayed (collections disabled)
├── _teaching/            # Not displayed (collections disabled)
└── _portfolio/           # Not displayed (collections disabled)
```

---

## Key Configuration

### 1. Collections Disabled (`_config.yml:211-223`)
All Jekyll collections have `output: false` to prevent generating individual pages:
- teaching
- publications
- portfolio
- talks

### 2. Navigation Stripped (`_data/navigation.yml`)
All navigation links are commented out. Only the homepage is accessible.

### 3. SEO Modifications (`_includes/seo.html:140-142`)
Added robots meta tag to discourage Google from showing sitelinks in search results.

---

## Content Guidelines

### Homepage Structure (`_pages/about.md`)

**Current sections** (in order):
1. **Brief intro** - One paragraph: current position, research focus, Ph.D. seeking status
2. **Education** - Degree, institution, years (reverse chronological)
3. **Publications** - Separated into "First Author" and "Co-authored"
4. **Experience** - Internships (reverse chronological)

**Writing style**:
- Direct and concise
- No lengthy descriptions
- Professional academic tone
- No placeholder text or template comments

---

## Deleted Pages

**DO NOT recreate these pages**:

- `/cv/` - Intentionally deleted (commit 075152b). If Google shows it in search results, this is expected and will resolve naturally as Google re-crawls.

---

## Common Tasks

### Update Publications
Edit `_pages/about.md`, publications section. Format:
```markdown
Author names. **Paper Title**. *Conference/Journal Name*, Year: Pages.
```

### Update Experience
Edit `_pages/about.md`, experience section. Keep descriptions to 1-2 sentences focusing on key outcomes.

### Change Contact Info
Edit `_pages/about.md` (email line) and `_config.yml` (author section).

---

## DO NOT

1. ❌ Create new pages in `_pages/`
2. ❌ Enable collections output in `_config.yml`
3. ❌ Uncomment navigation links in `_data/navigation.yml`
4. ❌ Recreate the CV page
5. ❌ Add verbose descriptions or template boilerplate

---

## Site Deployment

Push to `master` branch → GitHub Pages automatically builds and deploys.

Build time: ~2 minutes

---

## Search Engine Behavior

**Expected**: Google may show outdated links (CV, collections) for 1-4 weeks after deletion. This is normal and will self-correct.

**Solution**: Wait for natural re-indexing, or use Google Search Console to request removal.
