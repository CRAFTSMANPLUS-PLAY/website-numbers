# CRAFTSMAN+ Platform Intelligence

**Internal Use Only** — This tool is a data visualization and pricing analysis page built for internal review and website content development. It is intended to give Nick and the UA-facing team the numbers needed to communicate platform value on craftsmanplus.com.

---

## What This Is

A single-file HTML page that presents CRAFTSMAN+ SAAS platform performance data in a clean, interactive format. Styled to match the CRAFTSMAN+ help center aesthetic (dark theme, Poppins, brand colors). No frameworks, no build step — open it in a browser and it works.

---

## File Structure

```
/
├── craftsman_platform_intelligence.html   ← Main file
├── LOGO_LIGHT_CRAFTSMAN_PLUS.png          ← Logo (must be in same directory)
└── README.md                              ← This file
```

> **Important:** The logo image must live in the same directory as the HTML file. If you move the HTML, move the logo with it.

---

## Sections

### Executive Summary
The main landing section. Built for Nick and UA managers to pull key data points for the website.

- **Hero stats** — median cost per playable, platform savings vs agency, total exports all-time, total assets created
- **Cost breakdown** — min / median / avg / max for both cost per playable and cost per asset, with visual bars
- **Synergy of Scale** — interactive pricing calculator (see below)

### Platform Benchmarks
Detailed stat cards for cost per playable, cost per asset, and monthly export volume. Includes data quality notes explaining which months were excluded and why.

### Partner Breakdown
Full partner table sorted by contract value. Shows avg / min / max cost per playable and monthly export volume per partner, with above/below market indicators.

---

## Interactive: Synergy of Scale

The most UA-facing section. Located at the bottom of the Executive Summary tab.

**Seat selector (buttons 1–10 + Unlimited)**
- Click any number to select a seat count
- Monthly cost updates based on the pricing model:
  - 1 seat: $2,500/mo
  - Each additional seat: +$1,000/mo
  - 10+ seats: $12,000/mo (Unlimited)
- Stat cards update live: exports at tier, effective cost/export, savings vs agency

**Export volume slider**
- Drag to set monthly export volume (1–100)
- Updates three readout cards: cost per export at that volume, agency equivalent cost, % savings
- Synced with chart hover — moving the slider moves the crosshair on the chart and vice versa

**Chart (3 lines)**
- 🟠 **Orange** — CRAFTSMAN+ cost per export at the selected seat tier (curves down as volume grows)
- 🔴 **Coral** — Agency flat rate ($3,000/export, horizontal)
- 🟡 **Gold** — Platform median observed cost/playable ($385, horizontal reference)

When the orange curve drops below the gold line, the user is at efficient scale — producing at or below the platform median.

---

## Data Notes

All data sourced from the SAAS Closed Deals Monday board, refined sheet (`saas closed deals (1)`).

| Filter applied | Reason |
|---|---|
| Excluded months with < 2 exports | Removes single-export billing anomalies (Adikteev $17,857; T-Mobile legacy $20,625) |
| Excluded $0 contract value partners | Not active/relevant for benchmarking |

**Key numbers (post-filter):**

| Metric | Value |
|---|---|
| Median cost / playable | $385 |
| Average cost / playable | $1,136 |
| Min cost / playable | $30 |
| Max cost / playable | $8,928 |
| Savings vs $3,000 agency rate (median) | 87% |
| Total exports all-time | 4,062 |
| Total assets created all-time | 4,276 |
| Active data points used | 145 months across 17 partners |

---

## Colors

| Name | Hex | Usage |
|---|---|---|
| Orange | `#FA6C00` | Primary brand, savings, active states |
| Coral | `#EB5173` | Agency cost, above-market indicators |
| Gold | `#FEC01F` | Platform median reference, slider thumb |

---

## Dependencies

Loaded via CDN — no install required.

- [Poppins](https://fonts.google.com/specimen/Poppins) — Google Fonts
- [Chart.js 4.4.0](https://www.chartjs.org/) — cdnjs.cloudflare.com

The page requires an internet connection to load the font and chart library. For a fully offline version, these would need to be bundled locally.

---

## Deployment

This is a static file. To deploy:

1. Upload both `craftsman_platform_intelligence.html` and `LOGO_LIGHT_CRAFTSMAN_PLUS.png` to the same directory in your GitHub repo or hosting provider
2. No build process, no server required
3. Works with GitHub Pages, Netlify, Vercel static hosting, or any web server

---

## Ownership

Built from CRAFTSMAN+ internal SAAS data. Intended for internal review and website content development only. Not for external distribution.
