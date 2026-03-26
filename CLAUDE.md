# CLAUDE.md

## Project Overview

Static GitHub Pages website for **Exena Learning Hub**  - a Singapore-based WSQ-accredited team bonding workshop and training organisation. Hosted at `teamworkshops.exenalearninghub.org`.

## Repository Structure

```
├── CNAME              # Custom domain config for GitHub Pages
├── index.html         # Main marketing/landing page
├── proposal.html      # Interactive workshop proposal with costing calculator
├── teambonding.html   # Legacy marketing page (superseded by index.html)
└── CLAUDE.md          # This file
```

No build tools, package managers, or frameworks. Pure static HTML + CSS + JS.

## Pages

- **index.html**  - Professional marketing landing page. Sections: hero, stats, approach, programmes, activities, process, testimonials, clients, funding, gallery, other training, CTA, footer. Uses Inter font via Google Fonts, CSS custom properties, scroll-reveal animations (IntersectionObserver), and lazy-loaded media.
- **proposal.html**  - Interactive proposal tool sent to prospects. Features a WSQ funding calculator with live costing for Option A (1-day) and Option B (2-day), decision strip, copy/email integration, programme timeline, activity catalogue with video previews, and photo gallery.
- **teambonding.html**  - Legacy page (content merged into new index.html).

## Tech Stack

- **HTML5** with semantic elements
- **CSS3**  - embedded, using custom properties (`--navy`, `--accent`, `--teal`, etc.), flexbox, grid, `clamp()`, gradient backgrounds, backdrop-filter
- **JavaScript**  - vanilla JS for: scroll-reveal (IntersectionObserver), lazy loading (data-src pattern), costing calculator, sticky nav, decision strip, clipboard API
- **Google Fonts**  - Inter (400–900 weights)
- **No build step, no bundler, no package manager**

## Design System

- **Primary colors**: Navy `#0b1120`, Accent blue `#3b82f6`, Teal `#0d9488`
- **Typography**: Inter font family, weights 400–900
- **Border radius**: 16px (cards), 12px (smaller elements), 999px (pills)
- **Shadows**: Three tiers (`--shadow-sm`, `--shadow`, `--shadow-lg`)
- **Animations**: CSS transitions + IntersectionObserver `.reveal` class

## Development Workflow

1. Edit HTML files directly
2. Push to `master` branch to deploy via GitHub Pages
3. No CI/CD, tests, or linting configured

## Key Conventions

- **CSS classes**: kebab-case (e.g., `.feature-card`, `.section-title`, `.programme-grid`)
- **CSS custom properties**: defined in `:root`, used throughout
- **Lazy loading**: `data-src` attributes on images/iframes, loaded via IntersectionObserver
- **Costing calculator**: Defined in `proposal.html` with `OPTIONS` config object containing fees and absentee payroll rates per option
- **SETTINGS object**: At top of `proposal.html` for customising recipient, sender name/org/email

## Key Notes for AI Assistants

- **Never use em dashes** ( -) in any content. Use regular dashes (-) or rewrite the sentence instead.
- **Pure static site**  - no build commands, no tests
- All CSS is embedded in `<style>` tags (no external stylesheets except Google Fonts CDN)
- Images/videos are hosted on Google Drive (thumbnail API for images, file preview for videos)
- **Singapore audience**  - preserve SGD currency, local context, government scheme references (WSQ, SFEC, SkillsFuture, EIS)
- **WhatsApp CTAs** link to +65 9675 3242 (Ryan)
- **Email**: info@exenalearninghub.com (general), ryan@exenalearninghub.org (proposal)
- The `proposal.html` costing calculator is a critical feature  - test thoroughly when modifying fee structures
