# Retail Planning – Power BI report (PBIP)

Open `Retail_Planning.pbip` in Power BI Desktop, then **Refresh**.

- Data: `data/planning_weekly.csv` (3,744 rows, full weeks only)
- If you move this folder: Transform data → Manage parameters → `DataFolder` (must end with `\`)
- Save as `.pbix` (File → Save as) if you want a single file to share or publish.

## Model
Star schema: `Weekly` (fact) → `Weeks` (fiscal year, 4-week periods P1–P13, last-8-week flag), `Products` (short category names). `Bridge` drives the plan-to-actual waterfall.
Measures live in `Weekly` in display folders: 1 Sales & plan · 2 Forecast accuracy (WAPE/Bias computed at series × week grain) · 3 Inventory scenario (weeks of cover, receipt change).

## Pages
01 Sales performance · 02 Plan variance · 03 Forecast accuracy · 04 Inventory scenario · 05 Method & data
Values are on the dataset's scaled price index, not EUR.
