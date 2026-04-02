# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- `npm run dev` — Start dev server at localhost:4321
- `npm run build` — Production build to `./dist/`
- `npm run preview` — Preview production build locally
- Requires Node >= 22.12.0

## Architecture

Equipath marketing website built with **Astro 6** and **Tailwind CSS v4**.

- **Single-page site**: `src/pages/index.astro` is the only route, composing section components in order
- **Layout**: `src/layouts/Layout.astro` wraps all pages with head metadata, global CSS import, and a scroll-triggered `IntersectionObserver` for `.fade-up` animations
- **Components**: `src/components/` contains section components (Nav, Hero, Features, HowItWorks, WhoItsFor, BetaCTA, Footer) — all pure Astro, no framework integrations
- **Styling**: Tailwind v4 integrated via `@tailwindcss/vite` plugin in `astro.config.mjs`. Design tokens (colors, fonts) are defined in `src/styles/global.css` using `@theme {}` — edit tokens there, not in a tailwind config file
- **Deployment**: Configured for Azure Static Web Apps (`public/staticwebapp.config.json` handles SPA fallback and security headers)

## Design System

- Brand color: Equipath Blue `#062b5c` — all accent/CTA colors derive from this
- Fonts: Inter Tight (display + body), Playfair Display (serif accents) — loaded via Google Fonts in global.css
- Dark sections (hero, footer) use `.dark-section` utility class with `--color-dark-*` tokens
- CSS utility classes in global.css: `.fade-up`, `.card-hover`, `.gradient-text`, `.blob` / `.blob-light` (animated background shapes)
