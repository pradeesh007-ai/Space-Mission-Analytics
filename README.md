# Space Mission Analytics | Power BI Dashboard

An interactive Power BI portfolio project exploring **4,324 historical space mission records (1957–2020)**. The dashboard helps users explore launch activity over time, mission outcomes, organizational activity, and reported launch costs.

## Dashboard Preview

### 1. Mission Overview
![Mission Overview dashboard](Screenshot%202026-08-19%20165932.png)

### 2. Mission Performance Analysis
![Mission Performance Analysis dashboard](Screenshot%202026-08-19%20170231.png)

## Project at a Glance

| Item | Details |
|---|---|
| Project type | Data analytics and interactive dashboard |
| Dataset | 4,324 space mission records |
| Period covered | 1957–2020 |
| Organizations | 56 |
| Main tools | Power BI, Power Query, DAX |

## Business Questions

- How has global launch activity changed over time?
- What proportion of missions succeeded, failed, or partially failed?
- Which countries and organizations conducted the most launches?
- How can launch activity be explored by organization and rocket model?
- What launch costs are reported, and what limitations affect cost comparisons?

## Dashboard Pages

### Mission Overview
- KPI cards for total missions, successful missions, success rate, and organizations.
- Yearly and monthly launch trends.
- Launch activity by organization.
- Mission outcome distribution.
- Country and year filters.

### Mission Performance Analysis
- Decomposition tree to explore missions by country, organization, and rocket model.
- Gauge comparing the mission success rate with a 90% target.
- Matrix comparing organizations and mission outcomes.
- Launch-cost analysis using available reported cost values.

## Data Preparation

Power Query was used to remove unnecessary index columns, clean and standardize text, convert date values, split rocket model and payload from the detail field, and create useful date attributes. A separate Date Table was created and related to the mission records for time-based analysis.

**Missing launch costs were kept blank rather than replaced with zero.** This avoids presenting unknown costs as if they were free launches.

## Key Findings

- **4,324** missions in the dataset.
- **3,879** missions marked successful.
- **89.7%** overall success rate (3,879 divided by 4,324).
- **56** organizations represented.

## Tools and Skills Demonstrated

Power BI · Power Query · DAX · Data Modeling · Data Cleaning · Data Transformation · KPI Design · Data Visualization · Interactive Drill-Down Analysis

## Important Data Limitation

Launch-cost values are missing for a large share of records (approximately 77.7%). Cost visuals therefore represent **known/reported launch costs only**, not complete spending by an organization. The dataset's cost values are reported in USD millions. Mission outcomes also include separate categories for Success, Failure, Partial Failure, and Prelaunch Failure.

## Files

- [Download the Power BI dashboard (.pbix)](PowerBi%20project%28mission%20launch%29.pbix)
- [Read the analysis notes and measure definitions](ANALYSIS_NOTES.md)

## Dataset Source

[Space Mission Launches — Kaggle](https://www.kaggle.com/datasets/sefercanapaydn/mission-launches)

Dataset source and original usage terms are available at the link above. The CSV is not duplicated in this repository.

## How to View the Project

1. Open the `.pbix` file in Microsoft Power BI Desktop.
2. Use the Country and Year slicers to filter the dashboard.
3. Explore the charts and decomposition tree to investigate launch trends and organization performance.

## Author

**Pradeesh Kumar S**