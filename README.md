# NO3 Impact Fund — Marketing Site

Single-page marketing website for the **NO3 Impact Fund** — a German environmental impact fund deploying private capital into precision agriculture to reduce groundwater nitrate.

Built as a single HTML file with embedded CSS and vanilla JS, inspired by Stripe's visual language: weight-300 typography with tight negative tracking, tinted multi-layer shadows, conservative radii, and dense financial-grade data surfaces in a generously-spaced UI chrome.

## Preview

- Hero with live "Phase I" status card
- 3-card cost breakdown (utilities · government · GKV)
- Capital & outcome-payment flow diagram (SVG)
- Two-stream payment structure (Protocol compliance · Catchment performance)
- Full unit-economics waterfall table
- Animated J-curve (Chart.js) with breakeven marker and trough annotation
- Agronomic 200,000 ha → ~10,000 t NO₃/yr step-flow
- Scalability phases (Rhineland-Palatinate → Germany → EU)
- Full term sheet, target-investor cards, SDG contribution grid, partners row

## Tech Stack

| Layer      | Choice                                              |
|------------|-----------------------------------------------------|
| Markup     | Single `index.html`                                 |
| Styling    | Embedded CSS (no framework, custom property tokens) |
| Scripting  | Vanilla JS (IntersectionObserver, nav toggle)       |
| Charts     | [Chart.js](https://www.chartjs.org/) 4.x via CDN    |
| Typography | [Inter](https://rsms.me/inter/) via Google Fonts    |

No build step. No dependencies to install.

## Run locally

Open `index.html` directly in a browser, or serve it to get proper relative-path behaviour:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Then visit `http://localhost:8000`.

## Project structure

```
.
├── DESIGN.md          # Stripe-inspired design system reference
├── README.md
├── index.html         # The entire site (markup, styles, scripts)
└── src/
    └── Full Color.svg # Brand logo (uses currentColor for CSS-driven theming)
```

## Design tokens

Core palette lives in CSS custom properties inside `index.html` (`:root { --green-700: #1a7a5e; ... }`). Full system documentation — typography scale, shadow layering, spacing — is in [DESIGN.md](DESIGN.md).

| Role          | Token        | Value     |
|---------------|--------------|-----------|
| Brand primary | `--green-700`| `#1a7a5e` |
| Accent        | `--amber-500`| `#e8a020` |
| Heading       | `--ink-900`  | `#0b2a22` |
| Body          | `--ink-500`  | `#46615a` |
| Soft surface  | `--bg-soft`  | `#f7faf8` |
| Dark surface  | `--bg-dark`  | `#0b2a22` |

The brand mark in `src/Full Color.svg` fills with `currentColor`, so it inherits whatever CSS `color` you set on the containing element. Nav uses the original navy (`#073767`), footer uses white.

## Deployment

Any static host works — drop the three files onto Vercel, Netlify, Cloudflare Pages, or GitHub Pages.

**Vercel** — from the repo root:

```bash
npx vercel deploy
```

**GitHub Pages** — enable Pages in repo settings → Source: `main` branch, `/` root.

## Disclaimer

This site is for informational purposes only and does not constitute an offer to invest. Figures are illustrative of the pilot-phase vehicle (NO3 Impact Fund I).
