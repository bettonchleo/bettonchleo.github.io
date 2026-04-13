# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static academic personal website for Chleo Betton (PhD Candidate in Economics). No build tooling — pure HTML + CSS. Intended for deployment on GitHub Pages at `username.github.io`.

## Structure

```
index.html      — Full-screen split-layout hero (photo left, text right); no nav bar
about.html      — Bio, research interests, news; inner-page layout with sticky nav
research.html   — Working papers and work in progress
teaching.html   — Current and past courses
cv.html         — Full CV with PDF download button (expects files/cv.pdf)
contact.html    — Email, office, academic profile links
css/style.css   — Single shared stylesheet
images/         — Place profile photo here as photo.jpg
files/          — Place CV PDF here as cv.pdf
papers/         — Paper PDFs served directly
```

`index.html` is a standalone hero splash — it has inline styles and no `.site-nav`. All other pages share the sticky `.site-nav` + `.nav-links` pattern and `.page` main wrapper from `css/style.css`.

## Running Locally

Open any `.html` file directly in a browser. For PDF links:

```bash
python3 -m http.server 8000
```

## Design System

Blue theme. All tokens are CSS custom properties in `:root` at the top of `css/style.css`:
- `--blue` / `--blue-dark` / `--blue-pale` — primary accent palette
- `--bg-card` / `--bg-card-hover` — card backgrounds
- `--text` / `--text-muted` — type colours
- `--radius-pill: 50px` — pill button border-radius
- `--max-w: 780px` — content max-width

Typography: **DM Serif Display** (headings) + **Inter** (body), from Google Fonts.

Shared classes: `.btn-primary`, `.btn-outline`, `.card`, `.tag`, `.cv-entry`, `.cv-section`, `.course-row`, `.contact-item`, `.section-label`, `.divider`.

## Key Conventions

- Navigation `class="active"` is set manually on the matching `<a>` in each page's `<nav>`.
- All `[placeholder]` text in HTML files must be replaced with real content before publishing.
- To add a profile photo: place `photo.jpg` in `images/` and replace the `.hero-avatar-placeholder` / `.about-avatar-placeholder` divs with `<img src="images/photo.jpg" alt="Chleo Betton" class="hero-avatar" />` / `class="about-avatar"`.
- Cards have a left blue-border accent (4px) as a visual differentiator from the sibling lavender site.
- Mobile breakpoint is `max-width: 600px` (vs 480px in the sibling site).
