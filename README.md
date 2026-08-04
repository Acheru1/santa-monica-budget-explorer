# Santa Monica Budget Website

An interactive, resident-first explainer of the City of Santa Monica's budget. Single self-contained HTML page, Chart.js is inlined, so it works offline with no build step and no network access.

## Structure

```
.
├── index.html    # The entire site (markup, styles, data, and scripts inlined)
└── README.md
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
- Data objects, budget totals, revenue/spending breakdowns, and the department directory are defined as JS constants. Search for `const DEPARTMENTS` and the revenue/spending data arrays.
- Nav + sections, Overview, Money in, Money out, Your share (household calculator), Departments, About.
- Scripts, Chart.js setup, the Sankey flow, the household-share calculator, and the department search/filter.

If you want to split this into separate `styles.css` / `app.js` / `data.js` files, that's a reasonable next step now that it's in a real folder, say the word and I can refactor it.

## Data & caveats

- Headline citywide total is **net** of ~$115M interfund transfers ($796.6M). Fund list, balance trend, and Sankey use **gross** figures and are labeled as such.
- Household calculator defaults to General Fund (~$5,291/resident). Enterprise mode uses all-funds net (~$8,703/resident) with a fund breakdown scaled to that total.
- Property-tax "city share" (~14%) and hotel/utility/business/parking tax splitouts are rounded estimates and labeled in the UI.
- Independent project banner is shown above the fold; this is not an official City site.

## Accessibility

Skip link, single H1, semantic landmarks, chart table fallbacks, canvas `aria-label`s, keyboard-focusable Sankey nodes, `prefers-reduced-motion`, and a mobile list alternative for the Sankey.
