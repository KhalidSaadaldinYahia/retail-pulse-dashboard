# Retail Pulse

## Files

- [Open the Power BI dashboard](RetailPulse.pbix) in Power BI Desktop.
- [Read the PDF analytical preview](Retail_Pulse_Dashboard.pdf). This PDF summarises independently checked figures; it is not yet a page-for-page export of the PBIX. A matching PDF export is pending verification in Power BI Desktop.

The PBIX is the single-file dashboard. A data refresh may need network access to its saved source URLs.

## What the dashboard answers

- Which of the ten selected retail categories contributed most to the latest complete-year sales movement?
- How did 2025 sales compare with the comparable 2024 base?
- Which categories combine meaningful scale with positive or negative momentum?
- How do category and segment trajectories differ across the available period?

## Dashboard pages

- **Executive Overview** — complete-year KPIs, category contribution waterfall, and category scale ranking.
- **Market Momentum** — category growth-versus-scale analysis and prior-year benchmark.
- **Category Explorer** — interactive category trajectory and detailed benchmark table.
- **Methodology & Sources** — metric definitions, coverage, limitations, and interpretation guidance.

## Data and methodology

- **Source:** U.S. Census Bureau, Monthly Retail Trade Survey. [Monthly Retail Trade data](https://www.census.gov/retail/index.html). The 847-row source extract does not include the exact Census download URL, API request, retrieval date, seasonal-adjustment flag or category-code mapping. Those details cannot be independently reconstructed from the current repository; verify them against the original extract before making a source-certified claim.
- **Coverage:** January 2020 through May 2026.
- **Default executive comparison:** calendar year 2025 versus 2024, because 2026 is partial through May.
- **Units:** source figures are millions of current U.S. dollars; executive values are converted to USD billions.
- **Double-counting control:** the aggregate `Total Market` series is excluded from every selected-category KPI, contribution and ranking calculation. The ten displayed categories are a subset, not an exhaustive decomposition of the market.
- **YoY growth:** current sales minus the comparable prior-year sales, divided by that prior-year base. The extract starts in January 2020, so its 2020 prior-year and YoY fields are blank; no 2019 comparison is available.
- **Coverage reconciliation:** 2025 selected-category sales are $8,420.167 billion versus $8,695.398 billion for the separately published `Total Market` aggregate. The difference is $275.231 billion (3.2% of the market); the selected categories are not intended to sum to the aggregate.
- **Distance to complete-year peak:** selected/latest complete-year sales minus the highest annual sales in 2020–2025, divided by that peak. The 2026 partial year is excluded.

## Limitations

- Recent Census estimates may be revised.
- Values are current-dollar (not inflation-adjusted). The snapshot does not retain a seasonal-adjustment flag, so seasonal adjustment cannot be verified from these files.
- Partial 2026 results must not be interpreted as a complete-year decline.
- The dashboard is descriptive and does not establish causal relationships.
