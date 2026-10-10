# RideFlow — Trip Recovery Intelligence Dashboard

An Excel-based data analytics project designed to analyze ride-hailing performance, identify patterns in trip cancellations, and highlight opportunities to improve ride completion.

## Project Overview

Ride-hailing platforms need to match rider demand with available drivers while maintaining reasonable pickup times and fares. When rides are cancelled or no driver is matched, the platform may lose potential completed trips and deliver a poor customer experience.

**RideFlow** uses a synthetic dataset of 10,000 ride requests to analyze ride outcomes, estimated pickup times, city-level performance, hourly trends, and supply-demand conditions. An interactive Excel dashboard presents key performance indicators (KPIs), charts, and slicers to support business analysis.

> **Note:** This project uses synthetic data for learning and portfolio demonstration. Its findings are illustrative and do not represent actual ride-hailing company performance.

## Problem Statement

Ride-hailing platforms experience unsuccessful ride requests for several possible reasons, including rider cancellations, driver cancellations, long estimated pickup times, and insufficient driver availability.

The business challenge is to understand how these outcomes vary across cities, times of day, estimated pickup-time bands, and supply-demand conditions.

This project aims to build an analytical dashboard that helps answer the following questions:

- What percentage of ride requests result in completed trips?
- How frequently do riders and drivers cancel requests?
- How many requests remain unmatched?
- Which estimated pickup-time bands have higher rider cancellation rates?
- How does cancellation performance vary across cities?
- At what hours are cancellation rates relatively high?
- How do ride outcomes differ across supply-demand conditions?
- Which areas should be investigated further to improve trip recovery?

## Project Objectives

- Measure overall ride-request conversion and cancellation performance.
- Identify patterns in ride outcomes by city, hour, and estimated ETA band.
- Examine ride outcomes across supply-demand categories.
- Build an interactive Excel dashboard using charts, PivotTables, and slicers.
- Translate analytical observations into practical business investigation priorities.

## Dataset

- **Records:** 10,000 synthetic ride requests
- **Period:** 90-day period beginning January 1, 2026
- **Cities:** Mumbai, Pune, Bengaluru, Delhi, and Hyderabad
- **Format:** CSV, analyzed in Microsoft Excel
- **Data type:** Synthetic, generated for portfolio and educational purposes

### Key Fields

| Field | Description |
|---|---|
| `ride_id` | Unique ride request identifier |
| `request_timestamp` | Date and time of the request |
| `city` | City associated with the ride |
| `rider_type` | Rider category |
| `distance_km` | Requested trip distance |
| `estimated_fare_inr` | Estimated trip fare |
| `actual_fare_inr` | Actual fare field in the dataset |
| `surge_multiplier` | Surge pricing multiplier |
| `estimated_eta_min` | Estimated pickup time in minutes |
| `actual_pickup_min` | Actual pickup time in minutes |
| `active_drivers` | Active-driver count field |
| `supply_demand_ratio` | Supply-demand indicator |
| `ride_status` | Completed, Rider Cancelled, Driver Cancelled, or Unmatched |
| `cancellation_reason` | Recorded cancellation reason, where applicable |
| `driver_rating` | Driver rating field |
| `previous_rides` | Previous rides associated with the rider |
| `fare_difference_inr` | Difference between fare fields |
| `eta_difference_min` | Difference between actual pickup time and estimated ETA |
| `weekday` | Day of the week |
| `eta_band` | Categorized estimated pickup-time band |
| `completed_flag` | Completion indicator |

## Tools and Skills

- **Microsoft Excel:** Data exploration, formulas, structured tables, and dashboard design
- **Excel formulas:** `COUNTIF`, `COUNTIFS`, `AVERAGE`, and `IFERROR`
- **PivotTables and PivotCharts:** Ride-outcome analysis and interactive summaries
- **Slicers:** Interactive filtering by dimensions such as city and rider type
- **Data visualization:** KPI cards, bar charts, column charts, and line charts
- **Business analysis:** Cancellation analysis, performance measurement, and recommendations

## Key Performance Indicators

The dashboard tracks the following metrics:

- **Total Requests:** Total number of ride requests.
- **Completed Trips:** Number of requests marked Completed.
- **Completion Rate:** Completed trips divided by total requests.
- **Rider Cancellation Rate:** Rider-cancelled requests divided by total requests.
- **Driver Cancellation Rate:** Driver-cancelled requests divided by total requests.
- **Unmatched Rate:** Unmatched requests divided by total requests.
- **Average Estimated ETA:** Average estimated pickup time.
- **Average Estimated Fare:** Average estimated fare.
- **Average Surge Multiplier:** Average surge multiplier.

For cancellation and unmatched rates, the denominator is total requests unless explicitly stated otherwise.

## Dashboard Components

1. **KPI Cards** — Summarize total demand, completion rate, rider cancellation rate, and unmatched rate.
2. **ETA Analysis** — Compares rider cancellation rates across estimated pickup-time bands.
3. **City Analysis** — Compares cancellation performance across cities.
4. **Hourly Trend Analysis** — Examines how cancellation rates vary by hour.
5. **Ride Outcomes Analysis** — Compares completed, cancelled, and unmatched requests.
6. **Interactive Slicers** — Filter compatible PivotTables and PivotCharts by selected dimensions.
7. **Key Findings Panel** — Highlights areas for further investigation.

## Initial Findings

The synthetic dataset contains the following overall ride outcomes:

| Ride outcome | Requests | Percentage of all requests |
|---|---:|---:|
| Completed | 8,049 | 80.49% |
| Rider Cancelled | 1,114 | 11.14% |
| Driver Cancelled | 551 | 5.51% |
| Unmatched | 286 | 2.86% |
| **Total** | **10,000** | **100.00%** |

Initial exploratory analysis identified the following patterns:

- The **10–15 minute estimated ETA band** was identified as a priority for cancellation-rate investigation.
- **Mumbai** was identified as a city for further investigation.
- **7 PM** was identified as an hour to examine more closely.
- Supply-demand categories can help investigate whether ride outcomes vary with the balance between demand and driver availability.

These observations describe the generated dataset. They do not establish that ETA, city, time, or supply-demand conditions caused cancellations.

## Business Recommendations

Based on the observed patterns, the next analytical steps would be:

1. **Investigate longer ETAs:** Compare cancellation rates across ETA bands and examine whether the pattern persists across cities and rider types.
2. **Review city-level performance:** Compare request volumes and cancellation rates to identify where additional investigation may be valuable.
3. **Examine peak-hour conditions:** Analyze driver availability, request volumes, surge multipliers, and cancellation outcomes around 7 PM.
4. **Evaluate supply-demand conditions:** Compare completion, cancellation, and unmatched rates across supply-demand categories.
5. **Prioritize using both rate and volume:** A high cancellation rate with few requests may require a different response from a moderate rate affecting many requests.
6. **Validate with real operational data:** Test these hypotheses using actual ride requests, dispatch events, driver availability, and cancellation reasons before making operational decisions.

## Project Structure

Suggested GitHub repository structure:

```text
RideFlow-Trip-Recovery-Dashboard/
├── README.md
├── data/
│   └── rideflow_synthetic_rides.csv
├── dashboard/
│   └── RideFlow_Trip_Recovery_Dashboard.xlsx
├── screenshots/
│   └── dashboard_preview.png
└── scripts/
    └── generate_rideflow_data.py
```

Include only files that you actually upload to the repository. If you do not include the generator script or screenshots, remove those entries from this structure.

## How to Use the Project

1. Download the Excel workbook from the repository.
2. Open it in a compatible desktop version of Microsoft Excel.
3. Navigate to the Dashboard sheet.
4. Use the available slicers to filter compatible PivotTables and PivotCharts.
5. Review the KPI cards and visualizations.
6. Use the Analysis sheet and supporting PivotTables to investigate the patterns in more detail.

If the dataset changes, refresh the relevant PivotTables and verify that formulas, charts, and KPI cards are updated correctly.

## Limitations

- The dataset is synthetic and does not represent real customers or actual company operations.
- Observed patterns are descriptive and do not demonstrate causality.
- The analysis depends on the assumptions used to generate the data.
- Any proposed business actions require validation against real-world operational data.

## Future Improvements

- Add Power Query for repeatable data preparation.
- Develop a Power BI version of the dashboard.
- Add cohort and weekday-versus-weekend analysis.
- Analyze cancellation reasons and fare differences in greater detail.
- Add scenario analysis to estimate potential improvements in completed trips.
- Validate findings using real operational data, where available and appropriately authorized.

## Author

**Meet Badjatya**

Data Analytics Portfolio Project | Excel Dashboard | Business Analysis

