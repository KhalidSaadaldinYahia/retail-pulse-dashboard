# Retail Pulse

A Power BI retail intelligence dashboard built from the U.S. Census Bureau Monthly Retail Trade Survey.

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

- **Source:** U.S. Census Bureau, Monthly Retail Trade Survey. [Monthly Retail Trade data](https://www.census.gov/retail/index.html). The supplied 847-row CSV snapshot does not include the exact Census download URL, API request, retrieval date, seasonal-adjustment flag or category-code mapping. Those details cannot be independently reconstructed from the current repository; verify them against the original extract before making a source-certified claim.
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

## Open and inspect the report

- [Preview the dashboard PDF](Retail_Pulse_Dashboard.pdf). This PDF is a newly calculated, source-backed data preview; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/retail-pulse-dashboard/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`RetailPulse.pbip`](project/RetailPulse.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository at fixed commit `b79ca3348d32`. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

**Aggregation correction:** The base DAX measures now exclude the aggregate `Total Market` row so it cannot be added to its component categories. Source CSV dollar values are in **USD millions**; divide by 1,000 to express them in **USD billions**. The 2025 selected-category total is USD 8,420.167 billion. The source-unit charts and tables retain USD millions; the cards and charts explicitly labeled USD billions divide those values by 1,000. The PDF preview has been rebuilt from the corrected committed CSV snapshot.

### Reproducible data snapshot

The semantic model reads CSV files from immutable commit `b79ca3348d32f9c9a182d4bf7a501aab949f7f63`. The same files are included in `project/data/` for inspection. Refreshing this project will not silently switch to a later `main` branch snapshot. To analyze newer data, update the CSV and source URL together and revalidate the measures and preview.
