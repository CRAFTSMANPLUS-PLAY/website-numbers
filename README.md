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

## Navigation

Four tabs in the top nav bar (logo left, nav and badge right):

| Tab | Purpose |
|---|---|
| **Executive Summary** | Hero stats, cost breakdown, and the full Synergy of Scale interactive tool |
| **KPIs** | All key numbers in a clean quick-glance format for Nick |
| **Platform Benchmarks** | Detailed stat cards with data filter notes |
| **Partner Breakdown** | Full partner table sorted by contract value |

---

## Sections

### KPIs
The fastest way for Nick to pull numbers for the website. Five groups, no charts, pure data:
- Cost efficiency vs. agency ($3,000 benchmark, 87% savings, 99% best case)
- Cost per playable (min / median ★ / avg / max)
- Cost per asset created (min / median ★ / avg / max)
- Platform volume (total exports, total assets, active partners)
- Monthly export rate (min / median / avg / max)
- Pricing tiers ($2,500 base → $12,000 unlimited)

★ = recommended marketing anchor

### Executive Summary
Hero stats for UA managers plus the full **Synergy of Scale** interactive pricing calculator (see below).

### Platform Benchmarks
Detailed stat cards for cost per playable, cost per asset, and monthly export volume. Includes data filter notes.

### Partner Breakdown
Full partner table sorted by contract value. Shows avg / min / max cost per playable and avg monthly exports per partner (zero months excluded), with above/below market indicators.

---

## Interactive: Synergy of Scale

Located at the bottom of the Executive Summary tab.

**Seat selector (buttons 1–10 + Unlimited)**
- 1 seat: $2,500/mo
- Each additional seat: +$1,000/mo
- Unlimited (10+ seats): $12,000/mo flat
- Stat cards update live: exports at tier, effective cost/export, % savings vs agency

**Export volume slider**
- Drag to set monthly export volume (1–100)
- Synced with chart hover — moving the slider moves the crosshair on both charts simultaneously

**Two side-by-side charts**

| Chart | Color | What it shows |
|---|---|---|
| Cost per Export | Orange | Seat cost ÷ exports/month — curves down as volume grows |
| Cost per Asset | Gold | Seat cost ÷ assets/month — curves down in parallel |
| Agency rate | Coral dashed | Flat $3,000 reference line on both charts |

Both charts share the same slider. Hovering either chart syncs the slider and updates all readout cards. Each chart has its own live readout below showing the cost at the current volume.

---

## Data Notes

All data sourced from the SAAS Closed Deals Monday board, refined sheet (`saas closed deals (1)`).

### Filters Applied

| Filter | Reason |
|---|---|
| Cost per playable: exports ≥ 2/mo | Removes single-export billing anomalies (Adikteev $17,857; T-Mobile legacy $20,625 at 0 exports) |
| Cost per asset: assets_created ≥ 2/mo | Removes low-asset months inflating cost (T-Mobile $22,000 at 1 asset → $11,000 at 2 assets) |
| Avg exports/mo: zero months excluded | Prevents zero-output months from skewing partner averages (Niantic, Inmobi) |
| Partners with $0 contract value | Not active/relevant for benchmarking |

### Key Numbers (post-filter)

| Metric | Value |
|---|---|
| Median cost / playable | $385 |
| Average cost / playable | $1,136 |
| Min cost / playable | $30 |
| Max cost / playable | $8,928 |
| Savings vs $3,000 agency (median) | 87% |
| Savings vs $3,000 agency (best case) | 99% |
| Median cost / asset created | $346 |
| Average cost / asset created | $1,240 |
| Min cost / asset created | $42 |
| Max cost / asset created | $11,000 |
| Total exports all-time | 4,062 |
| Total assets created all-time | 4,276 |
| Active partners | 17 |
| Median exports / month | 8 |
| Average exports / month | 22 |
| Max exports / month | 211 (Ludus Ventures, Month 06) |
| Active data points used | 145 months (cost/playable) · 165 months (cost/asset) |

---

## Colors

| Name | Hex | Usage |
|---|---|---|
| Orange | #FA6C00 | Primary brand, savings, active states, cost per export |
| Coral | #EB5173 | Agency cost, above-market indicators, accent |
| Gold | #FEC01F | Cost per asset, slider thumb, median highlights |

---

## Layout

- **Top nav**: logo anchored left via `margin-right: auto`; nav links and "Internal Use Only" badge anchored right
- **Content**: centered, max-width 920px, no sidebar
- **Responsive**: single column on narrow viewports

---

## Dependencies

Loaded via CDN — no install required.

- Poppins — Google Fonts
- Chart.js 4.4.0 — cdnjs.cloudflare.com

> Requires an internet connection to load the font and chart library. For a fully offline version, these would need to be bundled locally.

---

## Deployment

Static file — no build process required.

1. Upload both `craftsman_platform_intelligence.html` and `LOGO_LIGHT_CRAFTSMAN_PLUS.png` to the same directory
2. Works with GitHub Pages, Netlify, Vercel, or any static host

---

## Ownership

Built from CRAFTSMAN+ internal SAAS data. For internal review and website content development only. Not for external distribution.
