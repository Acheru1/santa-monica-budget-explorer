# Budget source documents

Official City of Santa Monica budget PDFs used as the raw source for figures on this site. The live site still embeds numbers in `index.html`; these files are the audit trail and the place to pull new breakdowns from.

Index page: [Santa Monica Budgets & Annual Financial Reports](https://www.santamonica.gov/santa-monica-budgets-and-annual-financial-reports)

## FY 2025-27 pack (`fy2025-27/`)

| File | What it is | Official URL |
| --- | --- | --- |
| `FY2025-27-Adopted-Biennial-Budget.pdf` | Adopted biennial budget book (narratives, fund summaries, revenue/spend tables) | [PDF](https://www.santamonica.gov/media/Finance/Budgets%20&%20Reports/FY%202025-27%20Adopted%20Biennial%20Budget..pdf) |
| `FY2025-27-Operating-Budget-Line-Item.pdf` | Line-item operating detail by department/fund | [PDF](https://www.santamonica.gov/media/Finance/Budgets%20%26%20Reports/2026/2025-27%20Operating%20Budget%20Line%20Item.pdf) |
| `FY2024-26-Capital-Budget.pdf` | CIP / capital improvement program (FY 2024-26 cycle; FY25-26 is the exception year) | [PDF](https://www.santamonica.gov/media/Finance/Budgets%20&%20Reports/2025/2025%20Capital%20Budget.pdf) |
| `FY2025-27-Proposed-Biennial-Budget.pdf` | Proposed (pre-adoption) book for comparison | [PDF](https://www.santamonica.gov/media/Finance/Budgets%20&%20Reports/FY_2025_2027_Proposed_Biennial_Budget_Digital.pdf) |

Searchable plain-text extracts of each PDF live in `fy2025-27/text/` (one `.txt` per PDF, page markers as `===== PAGE N =====`). Prefer grepping those when answering “what’s in this number?” questions.

`manifest.json` lists filenames, byte sizes, SHA-256 hashes, and source URLs.

## Notes

- The City also publishes a file labeled “2025-27 Operating Budget” that is byte-identical to the Adopted Biennial Budget PDF; we keep only the Adopted copy.
- These are City documents, not City-endorsed products of this site.
- Re-download with a normal browser User-Agent if a bare `curl` gets HTTP 403.
