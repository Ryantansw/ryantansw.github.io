# CLAUDE.md

## Project Overview

Static GitHub Pages website for **Exena Learning Hub** — a Singapore-based team bonding workshop and training organization. Hosted at `teamworkshops.exenalearninghub.org`.

## Repository Structure

```
├── CNAME              # Custom domain config for GitHub Pages
├── index.html         # Interactive workshop proposal page (~2,650 lines)
├── teambonding.html   # Marketing/landing page for team bonding workshops (~490 lines)
└── CLAUDE.md          # This file
```

There are no build tools, package managers, frameworks, or external dependencies beyond Google Fonts CDN.

## Pages

- **index.html** — Workshop proposal/decision tool with collapsible sections, lazy-loaded media, pricing tables, and government funding info. Uses CSS custom properties for theming (`--accent: #2563eb`).
- **teambonding.html** — Marketing landing page listing 17 activity options, WSQ-funded programme details, testimonials, and WhatsApp contact CTAs.

## Tech Stack

- **HTML5** with semantic elements (`<section>`, `<details>`, `<article>`)
- **CSS3** — all inline/embedded, using custom properties, flexbox, and grid
- **JavaScript** — minimal vanilla JS for lazy-loading media (`data-src` pattern)
- **No build step, no bundler, no package manager**

## Development Workflow

1. Edit HTML files directly
2. Push to `master` branch to deploy via GitHub Pages
3. No CI/CD, tests, or linting configured

## Coding Conventions

- **CSS classes**: kebab-case (e.g., `.hero-grid`, `.section-title`, `.card-pad`)
- **Section IDs**: descriptive names (`#cover`, `#summary`, `#formats`, `#schemes`, `#agenda`, `#activities`, `#gallery`, `#moments`)
- **Lazy loading**: Use `data-src` attributes on images/iframes; JS loads them when parent `<details>` is toggled open
- **Language**: `lang="en-SG"` on index.html, `lang="en"` on teambonding.html
- **Color scheme (index.html)**: Blue accent `#2563eb`, CSS custom properties for theming
- **Color scheme (teambonding.html)**: Dark blue `#12375d` headings, teal `#137f5e` CTAs, light blue `#a8e0f0` hero

## Key Notes for AI Assistants

- This is a **pure static site** — no build commands to run, no tests to execute
- All CSS is embedded in `<style>` tags within each HTML file (no external stylesheets)
- Images and videos are hosted externally (Google Drive, external URLs) and lazy-loaded
- The site targets a Singapore audience — preserve SGD currency references and local context
- WhatsApp links are used for contact CTAs — preserve the phone number format
- Government funding references (WSQ, SFEC, SkillsFuture) are Singapore-specific schemes
