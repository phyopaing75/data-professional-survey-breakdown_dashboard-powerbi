# Data Professional Survey Breakdown: Power BI Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-View_Live_Report-F2C811?style=flat&logo=powerbi&logoColor=black)](https://app.powerbi.com/groups/me/reports/c68fc212-19d7-4ca4-b618-f606a598a514/d3a62572f739f858f3b7?ctid=96e7b82d-bfbf-4ce0-87c2-77981e8ab6b9&experience=power-bi)

---

## Project Overview

* Live Dashboard: [View the live Power BI report](https://app.powerbi.com/groups/me/reports/c68fc212-19d7-4ca4-b618-f606a598a514/d3a62572f739f858f3b7?ctid=96e7b82d-bfbf-4ce0-87c2-77981e8ab6b9&experience=power-bi)
* Tools and Technologies: Power BI Desktop, Power Query, DAX, Excel
* Dataset Scope: 630 responses to a survey of data professionals, with questions on job title, salary range, favourite programming language, happiness at work, how hard it was to break into data, age and country.
* Files: `Data Professional Survey Breakdown Project.pbix` (report), `Data Professional Survey Breakdown Dataset.xlsx` (data) and a PDF export of the dashboard.

---

## Business Problem

People who want a career in data, and the employers who hire them, need to know what working in the field looks like: which tools professionals prefer, what each role pays, how satisfied people are, and how hard it is to get in. The survey answers sit in a raw spreadsheet that is hard to read as it is. This project cleans the data and presents it in a single Power BI dashboard.

---

## Business Questions

| # | Business question | Dashboard visual |
|---|---|---|
| 1 | Who took the survey, and where do they live? | Count of Survey Takers and Average Age cards; Country of Survey Takers (treemap) |
| 2 | Which programming language do data professionals prefer? | Favorite Programming Languages (column chart by job title) |
| 3 | How much does each role pay? | Average Salary by Job Title (bar chart) |
| 4 | How happy are people with their pay and their work/life balance? | Happiness with Salary and Happiness with Work/Life Balance (gauges) |
| 5 | How hard is it to break into data? | Difficulty to Break into Data (donut chart) |

---

## Key Insights

All figures come from the visuals on the dashboard page.

1. **The survey has 630 respondents, with an average age of about 30.** The largest group is in the United States (261 respondents, 41.4%), followed by India (73), the United Kingdom (40) and Canada (32). Another 224 respondents (35.6%) are grouped as Other.
2. **Python is the favourite language by a wide margin.** It is chosen by 420 of 630 respondents (66.7%), against 101 for R and 95 for Other. Python is the most popular choice in every job title.
3. **Pay differs sharply by role.** Data Scientists have the highest average salary at about $93.8K, then Data Engineers ($65.1K), Data Architects ($63.7K), Other ($60.5K) and Data Analysts ($55.3K). Database Developers ($33.2K) and Students/Looking/None ($26.6K) are lowest. Data Architect has only 3 respondents and Database Developer 5.
4. **People are far less happy with their pay than with their work/life balance.** The average happiness score is 5.74 out of 10 for work/life balance and 4.27 out of 10 for salary.
5. **Most people did not find it easy to break into data.** 269 respondents (42.7%) said it was neither easy nor difficult, 156 (24.8%) said difficult and 44 (7.0%) said very difficult. Only 134 (21.3%) said easy and 27 (4.3%) very easy. In total, 74.4% found it neutral or harder.

---

## Recommendations

1. **Learn Python first.** It is the clear favourite in every role, so it is the safest first language for anyone starting a data career.
2. **Review pay for roles with low salary satisfaction.** Salary happiness (4.27) is well below work/life balance (5.74) and pay varies widely by role, so employers should benchmark salaries and communicate pay progression.
3. **Build clearer entry routes into data.** About a third of respondents (31.7%) found it difficult or very difficult to break in, so internships, mentoring and entry-level roles would widen the talent pool.

---

## Dashboard Design

| Visual | Type | Fields |
|---|---|---|
| Count of Survey Takers | Card | Count of `Unique ID` |
| Average Age of Survey Takers | Card | Average of `Q10 - Current Age` |
| Country of Survey Takers | Treemap | `Q11 - Which Country do you live in?`, count |
| Average Salary by Job Title | Bar chart | `Q1 - Job Title`, average of `Average Salary` |
| Favorite Programming Languages | Column chart | `Q5 - Favorite Programming Language`, count of responses by job title |
| Happiness with Work/Life Balance | Gauge | Average of `Q6 (Work/Life Balance)`, scale 0 to 10 |
| Happiness with Salary | Gauge | Average of `Q6 (Salary)`, scale 0 to 10 |
| Difficulty to Break into Data | Donut chart | `Q7 - How difficult was it to break into Data?`, count |

The page has no slicers.

---

## Data Preparation and Calculations

* **Power Query:** the survey table is prepared with data types set and the salary column split into bounds (see below).
* **Salary bands:** the survey asks for salary in ranges (`0-40k`, `41k-65k`, `66k-85k`, `86k-105k`, `106k-125k`, `125k-150k`, `150k-225k`, `225k+`). Each range is split into a lower and upper bound, and `Average Salary` is the midpoint in thousands of dollars (for example 53 for `41k-65k`). `225k+` is set to 225.
* **Calculations:** the dashboard uses Power BI's built-in aggregations on the survey columns (count, average, minimum and maximum). The model has no custom DAX measures.

---

## Data Notes

* **Data Analysts make up most of the sample** (381 of 630, 60.5%), so overall results lean towards that role.
* **Salary is approximate.** It is based on the midpoint of each salary range, so averages are estimates. The top range (`225k+`) is capped at 225K.
* **Small groups are less reliable.** Data Architect (3 respondents) and Database Developer (5) are too small to compare with the other roles.
* **The Students/Looking/None group** is included in the salary chart and pulls its average down (about $26.6K).
* **Other** appears as both a country (224 respondents) and a job title (88), so those groups are not specific.

---

## How to Open

1. Open `Data Professional Survey Breakdown Project.pbix` in Power BI Desktop.
2. If the data does not load, go to Transform data > Data source settings > Change Source and select your local copy of `Data Professional Survey Breakdown Dataset.xlsx`.
3. The PDF shows a static view of the dashboard.

---

## Repository Contents

| File | Description |
|---|---|
| `Data Professional Survey Breakdown Dataset.xlsx` | Survey data (630 responses) |
| `Data Professional Survey Breakdown Project.pbix` | Power BI report |
| `Data Professional Survey Breakdown Project.pdf` | PDF export of the dashboard |
| `README.md` | Project documentation |
