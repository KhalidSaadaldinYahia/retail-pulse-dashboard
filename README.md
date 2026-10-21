# Retail Pulse

A Power BI retail intelligence dashboard built from the U.S. Census Bureau Monthly Retail Trade Survey.

## What the dashboard answers

- Which retail categories contributed most to the latest complete-year sales movement?
- How did 2025 sales compare with the comparable 2024 base?
- Which categories combine meaningful scale with positive or negative momentum?
- How do category and segment trajectories differ across the available period?

## Dashboard pages

- **Executive Overview** — complete-year KPIs, category contribution waterfall, and category scale ranking.
- **Market Momentum** — category growth-versus-scale analysis and prior-year benchmark.
- **Category Explorer** — interactive category trajectory and detailed benchmark table.
- **Methodology & Sources** — metric definitions, coverage, limitations, and interpretation guidance.

## Data and methodology

- **Source:** U.S. Census Bureau, Monthly Retail Trade Survey.
- **Coverage:** January 2020 through May 2026.
- **Default executive comparison:** calendar year 2025 versus 2024, because 2026 is partial through May.
- **Units:** source figures are millions of current U.S. dollars; executive values are converted to USD billions.
- **Double-counting control:** the aggregate `Total Market` series is excluded from category-level contribution and ranking calculations.
- **YoY growth:** current sales minus prior-year sales, divided by prior-year sales.

## Limitations

- Recent Census estimates may be revised.
- Values are seasonally adjusted but are not inflation-adjusted.
- Partial 2026 results must not be interpreted as a complete-year decline.
- The dashboard is descriptive and does not establish causal relationships.

## Open and inspect the report

- [Preview the dashboard PDF](Retail_Pulse_Dashboard.pdf). A PDF is a static export; the `.pbip` project contains the interactive report.
- [Browse the Power BI project](project/) or [download this repository as a ZIP](https://github.com/KhalidSaadaldinYahia/retail-pulse-dashboard/archive/refs/heads/main.zip). Keep the `project` folder intact after extracting.
- Open [`RetailPulse.pbip`](project/RetailPulse.pbip) from the extracted `project` folder in a recent Power BI Desktop. The `.pbip` file references its sibling `.Report` and `.SemanticModel` folders; it cannot open by itself after downloading only that file.
- On refresh, choose **Anonymous** access if Power BI requests credentials for `raw.githubusercontent.com`. The project reads the included CSV snapshot from this repository's public `main` branch. For offline refresh, replace each table query's `Web.Contents(...)` CSV source with `File.Contents(...)` pointing to its included local `project/data` CSV.

The CSV data snapshots are included under [`project/data`](project/data/). A `.pbix` was not generated because the PBIP source cannot be converted faithfully without opening and saving it in Power BI Desktop.

**Aggregation correction:** The base DAX measures now exclude the aggregate `Total Market` row so it cannot be added to its component categories. Source CSV dollar values are in **USD millions**; divide by 1,000 to express them in **USD billions**. The 2025 category total is USD 8,420.167 billion. Some older PDF visuals still show Power BI auto-display suffixes applied to source-unit millions; use the corrected PBIP model and re-export the PDF for current values.
