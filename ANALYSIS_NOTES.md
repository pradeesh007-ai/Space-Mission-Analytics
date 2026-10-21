# Analysis Notes — Space Mission Analytics

This document explains the main preparation steps, model design, and measures used in the Space Mission Analytics Power BI dashboard.

## Data Overview

- Records: 4,324
- Date range: 4 October 1957 to 7 August 2020
- Organizations: 56
- Mission outcome categories: Success, Failure, Partial Failure, Prelaunch Failure
- Cost field: reported launch costs in USD millions, with many blank values

## Data Preparation in Power Query

1. Removed the two unnecessary index columns.
2. Cleaned and trimmed text fields.
3. Standardized rocket status values to Active and Retired.
4. Split the location field to retain the launch location and country.
5. Converted the launch date to a date/time value using the appropriate locale.
6. Split the detail field into rocket model and mission payload.
7. Converted price to a numeric value while preserving missing costs as blank.
8. Added year, month, month number, and quarter fields for time analysis.

## Data Model

A separate Date Table spans 1 January 1957 through 31 December 2020. The Date Table is related one-to-many to the mission table through a date-only launch date column. Month names are sorted by month number so visuals display January through December in calendar order.

## Main DAX Measures

### Total Missions
```DAX
Total Missions =
COUNTROWS(mission_launches)
```

### Successful Missions
```DAX
Successful Missions =
CALCULATE(
    [Total Missions],
    mission_launches[Mission_Status] = "Success"
)
```

### Failed Missions
```DAX
Failed Missions =
CALCULATE(
    [Total Missions],
    mission_launches[Mission_Status] = "Failure"
)
```

### Success Rate
```DAX
Success Rate =
DIVIDE([Successful Missions], [Total Missions], 0)
```

### Failure Rate
```DAX
Failure Rate % =
DIVIDE([Failed Missions], [Total Missions], 0)
```

### Known Launch Cost
```DAX
Known Launch Cost =
SUM(mission_launches[Price])
```

### Average Known Launch Cost
```DAX
Average Known Launch Cost =
AVERAGE(mission_launches[Price])
```

### Total Organizations
```DAX
Total Organizations =
DISTINCTCOUNT(mission_launches[Organisation])
```

### Success Rate Target
```DAX
Success Rate Target = 0.90
```

## Interpretation Notes

- The success rate is successful missions divided by all records in the current filter context.
- The Failure Rate measure counts records whose status is exactly `Failure`. `Partial Failure` and `Prelaunch Failure` are shown separately in the outcome distribution and are not included in that measure.
- Blank costs are not treated as zero. `Known Launch Cost` is the sum of available reported values, not complete organizational spending.
- A total mission count and success rate can change when Country or Year slicers are used.
- The 90% gauge target is a dashboard benchmark, not an externally established industry standard.

## Dataset Source

[Space Mission Launches — Kaggle](https://www.kaggle.com/datasets/sefercanapaydn/mission-launches)