# IPL Analytics Dashboard (2008–2024) — End-to-End SQL & Power BI Project


## Project Overview
An end-to-end business intelligence project connecting PostgreSQL to Power BI Desktop to analyze 1,095 IPL matches and 260,000+ ball-by-ball deliveries from 2008 to 2024. Building directly on top of my [IPL SQL Data Cleaning & Analysis](https://github.com) pipeline, this interactive dashboard allows stakeholders to explore franchise dominance, toss probability, top run-scorers, and death-over bowling specialists across seasons and teams.

## Data Pipeline & Star-Schema Modeling
- Data Source: Cleaned PostgreSQL relational tables (`clean_matches` and `clean_deliveries`) imported into Power BI Desktop.
- Data Modeling: Built a One-to-Many (1:*) Star Schema linking `clean_matches[id]` (Dimension/Header table) to `clean_deliveries[match_id]` (Fact table).
- Measures Organization: Created a dedicated `_Measures` folder to store all custom DAX calculations cleanly.

## Key DAX Measures Created
- `Total Matches`: Counts total IPL games played across selected seasons and teams.
- `Total Runs` & `Batsman Runs`: Aggregates overall team runs and individual batter runs from ball-by-ball logs.
- `Total Wickets`: Tracks total dismissals across matches.
- `Toss Win %`: Uses `DIVIDE()` and `CALCULATE()` to compare matches won by the toss winner against total decided matches (50.59%).
- `Qualified Death Economy`: Evaluates bowling economy rates in overs 16–20 (`over >= 15`) filtered for bowlers with at least 300 death-over balls bowled.

## Key Business Insights
- Near Coin-Flip Toss Advantage: Teams winning the toss win 50.59% of decided matches, confirming that toss outcomes provide minimal overall advantage despite captains choosing to field first 64.29% of the time.
- Most Successful Franchises: Mumbai Indians and Chennai Super Kings lead all franchises in total match victories across IPL history.
- Death-Over Bowling Specialists: Sunil Narine (7.40), Lasith Malinga (7.80), and Ravichandran Ashwin (7.90) rank among the most economical death-over bowlers with 300+ balls bowled.
- Interactive Filtering: Dynamic dropdown slicers for Season and Team allow instant drill-down across all KPI cards, bar charts, donut visuals, and bowling tables.

## Tools & Skills Demonstrated
- BI & Visualization: Power BI Desktop, Custom Dark Theme Design, KPI Cards, Clustered Bar Charts, Donut Charts, Interactive Slicers, Top-N Visual Filtering
- DAX Formulas: `CALCULATE()`, `DIVIDE()`, `COUNTROWS()`, `SUM()`, `IF()`, `BLANK()`
- Backend Integration: PostgreSQL Database Connection & Relational Star-Schema Modeling
