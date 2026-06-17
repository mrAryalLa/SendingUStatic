# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Site Is

SendingU.com is a static "coming soon" landing page for a planned global gift-sending platform (any country to any country). There is no backend, build system, or JavaScript framework — it is plain HTML/CSS/JS served via IIS from `C:\inetpub\SendingUStatic\SendingUStatic`.

## Serving / Previewing

There is no dev server or build step. Open `index.html` directly in a browser, or deploy to IIS. No compilation, no bundling, no package manager.

## File Layout

| File | Purpose |
|---|---|
| `index.html` | The entire page — announcement bar, sticky header, hero, 3 feature cards, notify section, footer |
| `css/styles.css` | All styles. Written mobile-first (base = mobile, `min-width` breakpoints for 600 px and 720 px) |
| `js/gtag.js` | Google Analytics 4 tag (`G-9XHFSZW3N8`) — just the gtag init snippet |
| `images/logo.png` | SendingU logo; referenced in the header |

## Design System

- **Colors**: `--logo-red: #e63946`, `--primary: #4b6fff` — used for all brand accents, gradients, and card top-border strips
- **Gradients**: hero CTA button and card top borders use `linear-gradient(135deg, var(--logo-red), var(--primary))`
- **Breakpoints**: `600px` (tablet header/spacing), `720px` (3-column card grid)
- **Animations**: `.announce-dot` and `.badge-dot` share the `pulse` keyframe (opacity + scale)

## Key Conventions

- CSS is mobile-first — default rules target small screens; desktop overrides live at the bottom under `@media (min-width: …)`
- The "coming soon" tone is intentional throughout — copy should remain in "launching soon / notify me" framing, not "start gifting now"
- The CTA button (`primary-btn`) and the "Get early access" button both `mailto:` to `reachme@SendingU.com` with pre-filled subjects; there is no form or backend
- `#year` in the footer is populated by an inline `<script>` using `new Date().getFullYear()`
- Google Analytics ID is `G-9XHFSZW3N8` — do not change it
