# Santa Monica Budget Website

An interactive, resident-first explainer of the City of Santa Monica's budget. Single self-contained HTML page, Chart.js is inlined, so it works offline with no build step and no network access.

## Structure

```
.
├── index.html              # The entire site (markup, styles, data, and scripts inlined)
├── README.md
└── sources/                # Official City budget PDFs + text extracts for lookup
    ├── README.md
    ├── manifest.json       # Filenames, SHA-256, page counts, City URLs (FY 2025-27 pack)
    ├── fy2025-27/          # Biennial book, line-item, capital, proposed
    └── fy2026-27-adoption/ # June 23, 2026 mid-cycle adoption (headline source)
```

## Run it locally

Just open `index.html` in a browser:

```bash
open index.html          # macOS
```

Or serve it (nicer for hot-reload while editing):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Editing in Cursor

Everything lives in `index.html`. The main sections, in order:

- `<style>`, design tokens (CSS custom properties) at the top, then component styles.
- Data objects, budget totals, revenue/spending breakdowns, and the department directory are defined as JS constants. Search for `const DIR`, `REV`, `SPEND`, and `TOTALS`.
- Nav + sections: Overview, Changes, Money in, Money out, Balanced?, Flow, Services, Self-funded, Engage, About (modal).
- Scripts: Chart.js setup, the Sankey flow, and the department search/filter.

If you want to split this into separate `styles.css` / `app.js` / `data.js` files, that's a reasonable next step now that it's in a real folder, say the word and I can refactor it.

## Data & caveats

- Default year is the **FY 2026-27 adopted plan** (June 23, 2026), with **FY 2025-26** as the prior-year plan for comparisons. Raw source PDFs live under `sources/` (see `sources/README.md` and `sources/fy2026-27-adoption/README.md`). Site figures are hardcoded in `index.html`; use the text extracts when verifying or adding detail.
- Headline citywide total is **net** of ~$118M interfund transfers ($908.8M this year). Fund list, balance trend, and Sankey use **gross** figures and are labeled as such.
- Per-resident KPIs divide spending by population (91,535 from the FY 2025-27 book). There is no interactive household calculator on the live page.
- Property-tax "city share" and hotel/utility/business/parking tax explainers are rounded estimates and labeled in the UI.
- Independent project banner is shown above the fold; this is not an official City site.

## Accessibility

Skip link, single H1, semantic landmarks, chart table fallbacks, canvas `aria-label`s, keyboard-focusable Sankey nodes, `prefers-reduced-motion`, and a mobile list alternative for the Sankey.
