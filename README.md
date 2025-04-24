# Cyclistic Case Study 🚴‍♀️

This project analyzes ride-sharing data from Cyclistic to understand the usage patterns of casual vs. member riders. The goal is to support data-driven marketing strategies for converting casual users into members.

**Tools used:** SQL (BigQuery), R (ggplot2, dplyr), RMarkdown

## Key Findings:
- Casual riders use bikes more often on weekends and have longer ride durations.
- Members ride more consistently throughout the week but with shorter durations.

[📄 Full Analysis Report (HTML)](./Cyclistic_Case_Study.html)

## SQL Summary (BigQuery)

The data was cleaned and transformed in BigQuery using the following logic:

- Extracted `ride_length` using `TIMESTAMP_DIFF(end_time, start_time, MINUTE)`
- Standardized user types: `Subscriber` → `member`, `Customer` → `casual`
- Extracted `day_of_week` using `EXTRACT(DAYOFWEEK FROM start_time)`
- Filtered out negative and zero-duration rides
- Exported summary table with fields: `member_casual`, `day_of_week`, `ride_length`

The resulting dataset was exported to CSV for further visualization in R.

