# Santa Monica Budget Website

An interactive, resident-first explainer of the City of Santa Monica's budget. Single self-contained HTML page — Chart.js is inlined, so it works offline with no build step and no network access.

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

- `<style>` — design tokens (CSS custom properties) at the top, then component styles.
- Data objects — budget totals, revenue/spending breakdowns, and the department directory are defined as JS constants. Search for `const DEPARTMENTS` and the revenue/spending data arrays.
- Nav + sections — Overview, Money in, Money out, Your share (household calculator), Departments, About.
- Scripts — Chart.js setup, the Sankey flow, the household-share calculator, and the department search/filter.

If you want to split this into separate `styles.css` / `app.js` / `data.js` files, that's a reasonable next step now that it's in a real folder — say the word and I can refactor it.

## Data & caveats

- All four headline budget totals tie to the source budget document exactly.
- Household calculator uses ~$5,291/resident × household size for share-of-spending.
- The property-tax "city share" (~14%) and the hotel/utility/business/parking tax split are illustrative/rough and labeled as such in the UI.

## Accessibility

Skip link, single H1, semantic landmarks, `aria-pressed`/`aria-live`, keyboard-focusable chart nodes, WCAG-AA contrast, and `prefers-reduced-motion` support.
