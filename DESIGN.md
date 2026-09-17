# Blum — Design System

> Luxury perfume for women. White canvas, blush pink accents, editorial serif headlines.

---

## 1. Brand Voice

| | |
|---|---|
| **Tone** | Quiet, considered, intimate. Writes like a letter, not an ad. |
| **Audience** | Women who value craft, scent longevity, and a soft-glam aesthetic. |
| **Tagline** | *"Bottled in quiet, meant to be worn."* |
| **Headline pattern** | Display serif headline + italic accent word in rose. |
| **Eyebrow** | UPPERCASE, letter-spaced (`tracking-[0.3em]`), color `blum-rose`. |
| **CTA voice** | Single primary verb — Shop, Explore, Subscribe — no "Buy now". |

---

## 2. Color Palette

Tokens are defined in `@theme` inside Tailwind 4 and exposed as utilities (e.g. `bg-blum-rose`).

### Primary

| Token | Hex | Role |
|---|---|---|
| `--color-blum-ink` | `#2b1d1f` | Headings, primary buttons, body text. Near-black with warm bias to read softer than pure black on pink. |
| `--color-blum-rose` | `#e8b4b8` | Primary accent — italics, eyebrows, badges, hover states. |
| `--color-blum-pink` | `#f7e1e1` | Surface tints, decorative gradients, promo backgrounds. |
| `--color-blum-blush` | `#f9eded` | Section backgrounds, soft card fills, hover surfaces. |

### Neutrals

| Token | Value | Role |
|---|---|---|
| `white` | `#ffffff` | Page background, primary surface. |
| `black/5` … `black/15` | rgba tints | Dividers, borders, muted icons. |
| `black/60` … `black/70` | rgba tints | Body copy secondary, captions. |

### Usage rules

- **Never** use a saturated pink as a page background — `blum-blush` is the loudest we'll go.
- The **only** saturated pink on the page is `blum-rose`, reserved for accents and hovers.
- Black sits at `#2b1d1f`, not `#000000` — keeps the palette warm and editorial.

---

## 3. Typography

Fonts loaded from Google Fonts:
- **Display:** Cormorant Garamond (serif, with italic)
- **Body:** Inter (sans-serif)

### Type scale

| Role | Class | Size | Weight | Notes |
|---|---|---|---|---|
| Hero headline | `font-display text-5xl md:text-7xl lg:text-[5.5rem]` | up to ~88 px | 300–400 | Italic accent word in rose. |
| Section headline | `font-display text-4xl md:text-5xl` | ~36–48 px | 400 | |
| Product title | `font-display text-xl` | 20 px | 500 | |
| Testimonial | `font-display text-2xl` | 24 px | 400 | |
| Eyebrow | `text-xs tracking-[0.3em] uppercase` | 12 px | 500 | Always rose. |
| Body | `text-sm` / `text-base` | 14 / 16 px | 400 | Inter. |
| Caption | `text-xs text-blum-ink/60` | 12 px | 400 | Ratings, prices, meta. |
| CTA | `text-sm tracking-wide` | 14 px | 500 | Sentence-case, not uppercase. |

### Rules

- Italics only on a single accent word inside a headline, never on whole headlines.
- Headlines use `leading-[1.05]` for editorial density.
- Generous `tracking` on small caps creates the "label" feeling.

---

## 4. Layout

### Container
```
max-w-7xl mx-auto px-6 lg:px-10
```
1280 px max width, 24 px gutter mobile → 40 px desktop.

### Section rhythm
- Vertical padding: `py-20 lg:py-28` (default), `py-24 lg:py-32` for "moment" sections.
- Inter-section spacing is whitespace, not dividers.

### Grid
- Product grids: `grid-cols-2 lg:grid-cols-4 gap-6`
- Category circles: `grid-cols-2 md:grid-cols-4 gap-5`
- Editorial 50/50 (discovery set, story): `grid lg:grid-cols-2 gap-10 lg:gap-16 items-stretch`

### Hero
- Full width, `aspect-[16/9]`, content left-aligned in container.
- Headline max-width `max-w-2xl`, paragraph `max-w-md`.

---

## 5. Border Radius

| Shape | Class | Used for |
|---|---|---|
| Pill | `rounded-full` | Buttons, icon containers, categories. |
| Card | `rounded-2xl` | Product cards, testimonial cards, journal cards. |
| Banner | `rounded-3xl` | Promo banners, hero overlays, large image frames. |

The pill is the dominant shape. Square corners would break the soft-feminine feel.

---

## 6. Buttons

| Variant | Class | When |
|---|---|---|
| **Primary** | `bg-blum-ink text-white px-7 py-3.5 rounded-full hover:bg-blum-rose` | Main CTA — Shop, Explore, Subscribe. |
| **Outline** | `border border-blum-ink/20 rounded-full px-5 py-2.5 hover:bg-blum-blush` | Secondary — View all, Read all. |
| **Text link** | `text-sm underline-offset-4 hover:underline` or with `border-b` | Tertiary — Our story → |
| **Icon round** | `w-9 h-9 rounded-full border border-blum-ink/15 hover:bg-blum-ink hover:text-white` | Cart, wishlist on cards. |

Padding tokens: `px-7 py-3.5` for full-size, `px-5 py-2.5` for compact.

---

## 7. Components

### Header
- Fixed, transparent at top, transitions to `bg-white/85 backdrop-blur shadow-sm` after 40 px scroll.
- Logo + 5 nav items + 3 icon buttons (search, account, cart with badge).
- Mobile: hamburger toggles drawer under header.

### Product card
- Aspect 4:5, rounded-2xl, placeholder bg `bg-blum-blush` or `bg-blum-pink/30`.
- Top-right: heart wishlist button (white circle).
- Top-left (optional): "New" pill badge.
- Below image: title (`font-display text-xl`), star rating, price + strikethrough, cart icon top-right.

### Category card
- Aspect-square circle (`rounded-full`) with name in `font-display text-3xl` centered.
- Subtle border in `blum-pink/40`, fill alternates between `blum-blush` and `blum-pink/40`.

### Promo banner
- `rounded-3xl`, `bg-blum-blush`, border `border-blum-pink/40`.
- Two-column: copy + CTA on left, stats grid on right (or below on mobile).

### Testimonial
- `border border-blum-pink/30 rounded-2xl p-8`, blockquote in display serif.
- Hover: `bg-blum-blush/50`.

### Newsletter
- Centered, max-w-3xl. Email input + primary button as a horizontal pair (`rounded-full`).
- Helper microcopy under, `text-xs text-blum-ink/50`.

### Footer
- Four-column on desktop, stacked on mobile.
- Top row: logo + tagline, then Shop / House / Help columns.
- Bottom row: copyright + social links.

---

## 8. Motion

| Trigger | Effect |
|---|---|
| Scroll into view | `.reveal` elements fade + translate up 20 px (`.9s ease`). |
| Product card hover | Inner image scales `1.04` over `.8s`. |
| Nav link hover | Underline grows from center, `.3s ease`. |
| Header scroll | Background swaps transparent → `bg-white/85 + backdrop-blur`. |
| Trust strip | Continuous marquee, 30 s linear. |

All transitions use ease curves, never linear. Keep durations under 1 s.

---

## 9. Imagery & Placeholders

Until real photography lands, image slots are styled div placeholders:
- Hero: `hero-placeholder` (pink radial-gradient + diagonal lines pattern).
- Product cards: text label in display serif on tinted background.
- Editorial blocks: aspect-ratio divs with a small `image · caption` in the corner.

When swapping in real images, the same aspect ratios (`16:9`, `4:5`, `4:3`, `5:4`) and rounded corners should be preserved.

---

## 10. Accessibility

- `aspect-[16/9]` (etc.) over hardcoded heights so layout doesn't break on resize.
- All icon buttons have `aria-label`.
- Form input uses native `type="email"` + `required`.
- Color contrast: `blum-ink` on white = 14:1 (AAA). `blum-rose` is accent only, never used for body copy.
- Focus styles rely on default browser outlines; production should add `focus-visible:ring-2 focus-visible:ring-blum-rose`.

---

## 11. File map

```
blum/
├── index.html        # Single-page landing, all sections inline
└── DESIGN.md         # This file
```

No build pipeline yet — Tailwind 4 runs from `@tailwindcss/browser` CDN. Move to a compiled pipeline before shipping.