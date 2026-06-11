# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML5 portfolio website for Jason Grant, built on the [Hyperspace HTML5 UP](https://html5up.net/hyperspace) template. No build system, no package manager — files are deployed directly to static hosting.

## Development

Since there's no build toolchain, development is straightforward:

- **View locally**: Open `index.html` in a browser, or serve with any static file server:
  ```
  python3 -m http.server 8080
  npx serve .
  ```
- **Edit styles**: Modify `.scss` files in `assets/sass/`, then compile to `assets/css/main.css`. If no SASS compiler is available, edit `assets/css/main.css` directly.
- **Compile SASS** (if sass CLI is available):
  ```
  sass assets/sass/main.scss assets/css/main.css
  sass assets/sass/noscript.scss assets/css/noscript.css
  ```

## Architecture

### Pages

- `index.html` — main landing page with sidebar nav, hero, spotlight grid, features, and contact form
- `web-development.html`, `seo-performance.html`, `data-and-analytics.html`, `ai-automation.html`, `ai-content-creation.html`, `creative-assets.html`, `certifications.html` — portfolio category pages
- `elements.html` — design system reference (all available components)

### JavaScript (`assets/js/main.js`)

jQuery-based. Handles: responsive breakpoints, sidebar toggle, smooth scroll via Scrollex/Scrolly plugins, spotlight scroll animations, contact form. Breakpoints are defined as named sizes (xxsmall → xlarge) and used throughout for responsive logic.

### SASS Structure (`assets/sass/`)

```
libs/         — variables, mixins, breakpoints, grid helpers
base/         — reset, page, typography
components/   — buttons, forms, icons, menu, spotlights, etc.
layout/       — header, footer, sidebar, intro, wrapper
main.scss     — imports everything above
```

### Third-Party Integrations

- **Contact form**: Formspree (`https://formspree.io/f/...` in `index.html`)
- **Analytics**: Google Analytics (GA-J8Z8YR09KZ), GTM (GTM-NPWXRSPM), Hotjar (5146657), Microsoft Clarity (o89ov2yagn)

### Images

All in `images/`. Portfolio uses WebP format for performance. Transparent variants of project mockups are named with `-transparent` suffix.
