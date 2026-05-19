# RevHounds — Design Guide
Version 1.0 | May 2026

---

## Brand Overview

RevHounds is a boutique hospitality revenue management consultancy. The brand is authoritative, analytical, and quietly confident — not flashy. The visual language mirrors that: dark, rich backgrounds; warm amber accents drawn directly from the logo hound; clean, legible typography; minimal decoration.

---

## Logo

- **Files**: `RevHounds.svg` (preferred), `RevHounds.png` (fallback), 'RevHounds-white.png' (used on dark backgrounds)
- **Minimum size**: 120px wide
- **Clear space**: equal to the cap-height of the wordmark on all four sides
- **Never**: recolor, rotate, add drop shadows, place on a busy background without a dark backing, or stretch
- **On dark backgrounds**: use with a light container behind it
- **On light backgrounds**: use the SVG/PNG as-is (logo was designed for light use)

---

## Color Palette

All colors defined as CSS custom properties in `style.css`.

| Token | Hex | Usage |
|-------|-----|-------|
| `--color-bg` | `#0d0d0d` | Page background |
| `--color-surface` | `#161616` | Card / section surface |
| `--color-surface-alt` | `#1e1e1e` | Alternate surface, nav bg |
| `--color-border` | `#2a2a2a` | Subtle borders |
| `--color-border-strong` | `#3d3d3d` | Hover borders |
| `--color-amber` | `#c98a2e` | Primary accent — pulled from logo |
| `--color-amber-light` | `#e8a94a` | Hover state for amber elements |
| `--color-amber-dim` | `rgba(201,138,46,0.12)` | Amber tints, highlights |
| `--color-text-primary` | `#f0ece4` | Headlines, primary body |
| `--color-text-secondary` | `#9a9389` | Subheadings, captions |
| `--color-text-muted` | `#5a5550` | Placeholder, disabled |
| `--color-white` | `#ffffff` | Pure white — use sparingly |

### Usage Rules
- Amber is the only accent color — never add blue, green, or red CTAs
- Text on amber: always use `#0d0d0d` (dark) for legibility
- Backgrounds layer: page → surface → surface-alt
- Use borders sparingly; rely on spatial separation and background contrast first

---

## Typography

| Role | Font | Weight | Size |
|------|------|--------|------|
| Display / Hero | Cormorant Garamond | 300–400 | 56–80px |
| Section Headings | Cormorant Garamond | 400 | 36–48px |
| Sub-headings | Cormorant Garamond | 500 | 20–28px |
| Body copy | DM Sans | 400 | 16px / 1.75 line-height |
| UI labels, nav | DM Sans | 500 | 13–15px |
| Eyebrow text | DM Sans | 600 | 11px, letter-spacing 0.15em, ALL CAPS |

### Rules
- Headlines are set in Cormorant Garamond — elegant and distinctive without being decorative
- Body text is DM Sans — neutral and highly legible
- All caps is reserved exclusively for eyebrow labels (section identifiers above headings)
- No bold headlines — the serif font's own weight contrast is the visual hierarchy

---

## Spacing System

Based on an 8px grid.

| Token | Value |
|-------|-------|
| `--space-xs` | 8px |
| `--space-sm` | 16px |
| `--space-md` | 32px |
| `--space-lg` | 64px |
| `--space-xl` | 96px |
| `--space-2xl` | 144px |

Section vertical padding: `var(--space-xl)` top and bottom (96px).
Container max-width: `1120px`, centered, with `24px` horizontal padding.

---

## Components

### Navigation
- Fixed top, `height: 72px`
- Background: `--color-surface-alt` with `1px` bottom border in `--color-border`
- Logo left-aligned; nav links right-aligned
- Active link: amber underline `2px` bottom
- Mobile: hamburger at `< 768px`, full-screen slide-down menu

### Buttons
- **Primary**: amber fill (`--color-amber`), dark text, `border-radius: 2px`, `padding: 12px 28px`
- **Ghost**: transparent fill, `1px` amber border, amber text
- Hover: 8% lighter on both
- No border-radius curves above `4px` — the brand is refined, not bubbly

### Service Cards
- Background: `--color-surface`
- Border: `1px solid --color-border`
- Top amber rule: `3px solid --color-amber`
- Padding: `32px`
- On hover: border becomes `--color-border-strong`, subtle `translateY(-4px)`

### Section Eyebrows
Pattern:
```
[amber line] EYEBROW TEXT [amber line]
```
`11px`, `0.15em` letter spacing, `--color-amber`

### Form Inputs
- Background: `--color-surface-alt`
- Border: `1px solid --color-border`
- Focus: border becomes `--color-amber`, no box-shadow
- Text: `--color-text-primary`
- Placeholder: `--color-text-muted`

---

## Imagery
- Use dark, atmospheric hotel/hospitality photography
- Prefer wide-ratio hero images (16:9 or wider)
- Apply an overlay: `rgba(13,13,13,0.55)` to maintain text legibility
- The existing team headshots on About are fine to keep as-is
- Avoid stock-photo clichés: handshakes, people staring at laptops, forced smiles

---

## Motion
- Transitions: `200ms ease` for hover states
- Section reveal: `opacity 0 → 1`, `translateY(20px → 0)` on scroll (IntersectionObserver)
- No auto-play video, no parallax
- Reduced motion: all animations respect `prefers-reduced-motion: reduce`

---

## Page Structure (Single Page)

1. **#home** — Hero with tagline + CTA
2. **#services** — Three service pillars + systems list
3. **#about** — Who we are + team cards
4. **#contact** — Contact form + email/phone

---

## File Structure

```
/
├── index.html          ← single page, all sections
├── style.css           ← all styles
├── RevHounds.svg  ← preferred logo
├── RevHounds.png  ← fallback
├── RevHounds-whitw.png  ← use on dark backgrounds
└── assets/             ← any additional images
```

---

## Deployment (Cloudflare Pages)

1. Push to a GitHub repo (even a private one)
2. In Cloudflare dashboard → Pages → Create project → Connect GitHub repo
3. Build settings: Framework = None, Build command = (leave empty), Output = `/` (root)
4. Set the custom domain `revhounds.com` in Pages > Custom Domains
5. Cloudflare will auto-provision SSL

### Contact Form (Web3Forms)
1. Go to [web3forms.com](https://web3forms.com) and enter `contactus@revhounds.com`
2. You'll receive an **Access Key** — replace `YOUR_WEB3FORMS_KEY` in `index.html`
3. No backend needed — Web3Forms handles delivery

---

*©2026 RevHounds LLC*
