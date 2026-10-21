# Space Mission Analytics — Power BI Dashboard

## Project Overview
An interactive Microsoft Power BI project analyzing 4,324 historical space mission records from 1957 to 2020. The dashboard explores launch trends, mission outcomes, organizational activity, and reported launch costs.

## Objectives
- Analyze yearly and monthly launch trends.
- Measure mission success and failure rates.
- Compare launches across countries and organizations.
- Explore available launch-cost data.

## Tools and Technologies
- Microsoft Power BI
- Power Query
- DAX
- Data Modeling
- CSV data

## Data Preparation
- Removed unnecessary index columns.
- Cleaned and standardized text fields.
- Converted dates and extracted rocket model and payload information.
- Preserved missing launch costs as blanks rather than treating them as zero.
- Created a Date Table and related it to the mission records.

## Dashboard Features
- Mission Overview with KPI cards.
- Yearly and monthly launch trends.
- Launches by organization.
- Mission outcome distribution.
- Decomposition tree for drilling into country, organization, and rocket model.
- Mission success-rate gauge.
- Organization mission performance matrix.
- Reported launch-cost analysis.

## Dashboard Preview

### Mission Overview
![Space Mission Analytics — Mission Overview](Screenshot%202026-08-19%20165932.png)

### Mission Performance Analysis
![Space Mission Analytics — Mission Performance Analysis](Screenshot%202026-08-19%20170231.png)

## Key Findings
- Total missions analyzed: 4,324.
- Successful missions: 3,879.
- Overall success rate: approximately 89.7%.
- Organizations represented: 56.

## Data Limitations
Launch-cost information is missing for many records. Cost charts therefore show reported/known launch costs and should not be interpreted as complete spending totals.

## Dataset
Source: [Space Mission Launches on Kaggle](https://www.kaggle.com/datasets/sefercanapaydn/mission-launches). The dataset is not included in this repository; refer to the source for access and usage terms.

## Project File
[Download the Power BI dashboard](PowerBi%20project%28mission%20launch%29.pbix)

## Author
Pradeesh Kumar S