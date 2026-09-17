# Blum — Luxury Perfume Landing

A single-page ecommerce landing for **Blum**, a luxury women's perfume brand. Built with HTML, vanilla JS, and Tailwind 4.

## Highlights

- **Scroll-scrub hero** — a 5-second video plays frame-by-frame, gated by scroll position. Smooth at any scroll speed because frames are pre-decoded and drawn to a GPU canvas.
- **Glassmorphic cart drawer** — slide-in from the right, persists to `localStorage`, event-delegated add/remove/qty actions.
- **Mobile-tuned** — 640×360 mobile frames, lazy-loaded in a ±25 window around the current scroll position, ~450 KB initial payload.
- **Compiled Tailwind 4** — 24 KB CSS instead of the 300 KB JS CDN.

## Run

Requires [pnpm](https://pnpm.io) (declared in `package.json` via `packageManager`).

```bash
pnpm install
pnpm run build       # compile Tailwind once
pnpm run watch       # recompile on save
open index.html      # or serve it
```

## Docs

- [`DESIGN.md`](DESIGN.md) — design system: colors, typography, components.