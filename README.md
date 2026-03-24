# Rendrx — Craft. Motion. Code.

A polished, single-page creative agency website built entirely with vanilla HTML, CSS, and JavaScript — no frameworks, no build tools, no dependencies beyond two Google Fonts.

---

## Overview

**Rendrx** is a showcase landing page for a creative studio offering three core services: **video production**, **motion graphics**, and **web development**. Every section is hand-crafted with custom canvas animations, smooth scroll-driven reveals, and a fully invertible dark/light theme system.

---

## Features

### UI & Interaction
- **Dark / Light theme** — full CSS variable system with smooth transitions and a flash overlay to prevent jarring colour shifts on toggle
- **Custom cursor** — dot cursor that scales on hover over interactive elements (desktop only)
- **Scroll progress bar** — 2 px line at the top of the viewport tracking page scroll position
- **Reveal animations** — elements fade and translate up as they enter the viewport via `IntersectionObserver`
- **Grain overlay** — subtle SVG fractal-noise texture applied site-wide for texture depth

### Loader
- Animated **Tetris canvas** loader with a progress bar and tagline ticker
- Clips away with a smooth `clip-path` transition once the page is ready

### Navigation
- Fixed nav that gains a frosted-glass background on scroll
- Active link indicator (dot underline)
- Full-screen **mobile menu** with large typographic links and a hamburger toggle

### Sections
| Section | Details |
|---|---|
| **Hero** | Full-viewport with animated particle canvas, floating stat cards, and a cycled italic word swap |
| **Marquee** | Auto-scrolling service ticker that pauses on hover |
| **Services** | Three alternating-layout sections (Video, Motion, Web) each with a unique live canvas visual |
| **Projects** | Filterable 3-column grid (All / Video / Motion / Web) with hover overlays and category accent lines |
| **Stats** | Fully inverted section (light block on dark page, dark block on light page) with four animated counters |
| **Process** | Four-step grid with connector arrows and icon badges |
| **Testimonials** | Three auto-scrolling columns of testimonial cards with masked edges |
| **Team** | Two-up card layout with lift-on-hover and large ghost numbers |
| **CTA** | Always-dark section with a starfield canvas, animated glow, and contact actions |

### Canvas Animations
- **Hero** — particle field
- **Loader** — playable Tetris game
- **Video service** — simulated NLE (non-linear editor) timeline
- **Motion service** — generative motion-graphics preview
- **Web service** — animated browser chrome mock-up with shimmer and blinking cursor
- **CTA** — starfield / night-sky background

---

## Tech Stack

| Layer | Choice |
|---|---|
| Markup | Semantic HTML5 |
| Styling | Vanilla CSS (CSS variables, Grid, Flexbox, `clamp()`) |
| Scripting | Vanilla JavaScript (ES6+, Canvas API, IntersectionObserver) |
| Fonts | [Arvo](https://fonts.google.com/specimen/Arvo) (serif headings) · [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (UI / body) via Google Fonts |
| Assets | `assets/` directory (logo mark PNG used as a CSS mask) |

No npm, no bundler, no framework.

---

## Project Structure

```
Agency_website/
├── index.html      # Entire site — markup, styles, and scripts in one file
└── assets/
    └── logo-mark.png   # SVG-compatible logo mask
```

---

## Getting Started

Because this is a pure static site, there is no build step.

**Option 1 — Open directly**

```bash
# Clone the repo
git clone https://github.com/UnrealZahid101894/Agency_website.git

# Open in your browser
open Agency_website/index.html
```

**Option 2 — Local dev server** (recommended to avoid CORS quirks with assets)

```bash
# Python
python -m http.server 8080

# Node (npx)
npx serve .
```

Then visit `http://localhost:8080`.

---

## Customisation

All design tokens live in the `:root` block at the top of the `<style>` tag inside `index.html`.

```css
:root {
  --bg: #0a0a0a;          /* page background */
  --text: #f0f0f0;        /* primary text */
  --text3: #707070;       /* muted / eyebrow text */
  --fd: 'Arvo', serif;    /* display / heading font */
  --fb: 'JetBrains Mono', monospace; /* body / UI font */
}
```

A parallel `[data-theme="light"]` block overrides every variable for the light mode.

To swap the agency name, tagline, service copy, project cards, team bios, and testimonials, search for the relevant text inside `index.html` — all content is inline.

---

## Browser Support

Targets modern evergreen browsers (Chrome, Firefox, Safari, Edge). The site uses:

- `CSS custom properties` — widely supported
- `IntersectionObserver` — no polyfill included; older browsers will see elements without reveal animation
- `Canvas 2D API` — required for loader, hero, and service visuals
- `backdrop-filter` — used for the scrolled nav; degrades gracefully where unsupported

---

## License

This repository is publicly available. Add a `LICENSE` file if you intend to distribute or use this commercially.

---

> Built by [UnrealZahid101894](https://github.com/UnrealZahid101894)
