# Retail Pulse — local review changes

- Corrected `YoY Growth` to divide the YoY change by prior-year sales rather than current sales.
- Added explicit `MonthNumber` and `MonthStart` fields to all 847 rows, preserving the verified category/year row order and yielding zero duplicate category-month keys.
- Added visible `2020–May 2026` and partial-2026 warnings; complete-year comparisons remain 2025 versus 2024.
- Replaced the copied Displacement Pulse `qa_summary.json` with retail-specific checks and recomputed complete-year totals.
- Replaced the obsolete local CSV path with a `DataFolder` Power Query parameter.
- Confirmed that the local README no longer references the missing `dashboard-preview.png`; the source package contains no preview asset.

The corrected complete-year result is $8,420.167B in 2025 versus $8,105.059B in 2024: +$315.108B, or +3.8878%. A native PDF re-export still requires Power BI Desktop.

- Removed unsupported 2020 prior-year and YoY values, aligned the 2025 growth card with ten selected categories, corrected the prior-year billion-unit chart and added a genuine complete-year peak measure.
