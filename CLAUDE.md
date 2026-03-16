# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website for KONATE Abas, a freelance Laravel back-end developer. The site is a static single-page site hosted on GitHub Pages at `konateabas.fr`.

## Architecture

- **Single-page static site** — no build step, no bundler, no package manager
- `index.html` — the entire site (sections: Accueil, Projets, À propos, Contact)
- `assets/css/main.css` — legacy stylesheet (currently unused by `index.html`, which uses Tailwind CDN)
- `assets/scriptPortfolio.js` — legacy JS file (currently empty/unused)
- `assets/images/` — all images, icons, and PDF CV
- `assets/woff_SF_apple/` — San Francisco font files
- `CNAME` — GitHub Pages custom domain (`konateabas.fr`)

## Development

No build or test commands. Open `index.html` directly in a browser or use any local HTTP server:

```
npx serve .
```

## Key Technical Details

- Styling uses **custom CSS with CSS variables** — no Tailwind, no framework
- Design system uses CSS custom properties in `:root` (colors: `--accent` amber/gold `#D4A853`, dark background `--bg` `#090909`)
- Typography: **Playfair Display** (serif, headings) + **DM Sans** (sans, body) via Google Fonts
- The site language is **French** (`lang="fr"`)
- Age is computed dynamically from `data-birthdate` attribute on `#age-pill`
- Footer year is set dynamically via inline `<script>`
- Scroll reveal animations use `IntersectionObserver` with `.reveal` / `.visible` classes
- Navigation has scroll-triggered background change and mobile hamburger menu
- `main.css` and `assets/scriptPortfolio.js` are legacy files, not currently used
