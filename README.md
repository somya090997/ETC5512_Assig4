# Assignment 4 | ETC5512 Wild-Caught Data
**Author:** Somya Verma  
**Title:** Does Gender Differences in Underemployment contribute to Underutilisation of Labour in Australia?

---

## Project Structure

After the feedback from tutor, the question was framed differently to bring more complexities in analysis and help
to showcase the skills in the best capacity. 

Question to investigate: Does Gender Differences in Underemployment contribute to Underutilisation of Labour in Australia?


---

## Data Source

All datasets were obtained from the **Australian Bureau of Statistics (ABS) Labour Force Survey**.  
URL: https://www.abs.gov.au/statistics/labour/employment-and-unemployment/labour-force-australia  
Licence: Creative Commons Attribution 4.0 International (CC BY 4.0)  
Access: Publicly available, no registration required.

---

## Raw Datasets

### 1. `Chart 1_ Underemployed workers, Original.csv`
- **Description:** Monthly total underemployed workers in Australia, original series.
- **Series Type:** Original
- **Frequency:** Monthly
- **Time Period:** 2016 – 2025

| Variable | Type | Description |
|---|---|---|
| `month` | chr → date | Reference month (format: Mon-YY) |
| `hours_reduced` | dbl | Workers who worked fewer hours than usual for economic reasons ('000) |
| `prefers_more` | dbl | Workers who prefer more hours than usual ('000) |
| `total_underemp` | dbl | Total underemployed workers ('000) |

---

### 2. `Chart 5_ Underemployed workers, by Sex, Original.csv`
- **Description:** Monthly underemployed workers split by sex, original series.
- **Series Type:** Original
- **Frequency:** Monthly
- **Time Period:** 2016 – 2025

| Variable | Type | Description |
|---|---|---|
| `month` | chr → date | Reference month (format: Mon-YY) |
| `male_prefers_more_hours` | dbl | Male workers preferring more hours ('000) |
| `male_hours_reduced` | dbl | Male workers with reduced hours for economic reasons ('000) |
| `female_prefers_more_hours` | dbl | Female workers preferring more hours ('000) |
| `female_hours_reduced` | dbl | Female workers with reduced hours for economic reasons ('000) |

---

### 3. `Underemployment rate and underutilisation rate.csv`
- **Description:** Monthly underemployment and underutilisation rates, trend and seasonally adjusted.
- **Series Type:** Trend and Seasonally Adjusted
- **Frequency:** Monthly
- **Time Period:** 2016 – 2025

| Variable | Type | Description |
|---|---|---|
| `month` | chr → date | Reference month (format: Mon-YY) |
| `underemployment_rate_trend` | dbl | Underemployment rate, trend series (%) |
| `underemployment_rate_sa` | dbl | Underemployment rate, seasonally adjusted (%) |
| `underutilisation_rate_trend` | dbl | Underutilisation rate, trend series (%) |
| `underutilisation_rate_sa` | dbl | Underutilisation rate, seasonally adjusted (%) |

---

### 4. `Unemployment rate.csv`
- **Description:** Monthly unemployment rates, trend and seasonally adjusted.
- **Series Type:** Trend and Seasonally Adjusted
- **Frequency:** Monthly
- **Time Period:** 2016 – 2025

| Variable | Type | Description |
|---|---|---|
| `month` | chr → date | Reference month (format: Mon-YY) |
| `unemployment_rate_trend` | dbl | Unemployment rate, trend series (%) |
| `unemployment_rate_sa` | dbl | Unemployment rate, seasonally adjusted (%) |

---

## Processed Datasets

### 5. `labour_data_processed.csv`
- **Description:** Master analysis dataset created by joining datasets 2, 3, and 4 on `month`, filtered to June 2016 – December 2025.

| Variable | Type | Description |
|---|---|---|
| `month` | date | Reference month |
| `male_prefers_more_hours` | dbl | Male workers preferring more hours ('000) |
| `male_hours_reduced` | dbl | Male workers with reduced hours ('000) |
| `female_prefers_more_hours` | dbl | Female workers preferring more hours ('000) |
| `female_hours_reduced` | dbl | Female workers with reduced hours ('000) |
| `underemployment_rate_sa` | dbl | Underemployment rate, seasonally adjusted (%) |
| `underutilisation_rate_sa` | dbl | Underutilisation rate, seasonally adjusted (%) |
| `unemployment_rate_sa` | dbl | Unemployment rate, seasonally adjusted (%) |
| `Tot_male_underemp` | dbl | Total male underemployment ('000) |
| `Tot_female_underemp` | dbl | Total female underemployment ('000) |
| `total_underemp` | dbl | Combined underemployment ('000) |
| `male_share` | dbl | Male share of total underemployment (%) |
| `female_share` | dbl | Female share of total underemployment (%) |
| `share_gap` | dbl | Male share minus female share (percentage points) |

---

### 6. `share_yearly_processed.csv`
- **Description:** Annual average gender shares of underemployment in long format, used for visualisation.

| Variable | Type | Description |
|---|---|---|
| `year` | int | Calendar year |
| `gender` | chr | Gender category (`male_share` or `female_share`) |
| `share` | dbl | Average annual share of total underemployment (%) |

---

## Important Notes

- The ABS notes increased volatility during the **COVID-19 period (April 2020 – March 2022)**; interpret labour market movements during this period with caution.
- Gender is recorded as binary (male/female) in ABS data. Non-binary and gender-diverse identities are not captured.
- All underemployment counts are in thousands ('000).
- Seasonally adjusted series were used for rates to remove recurring seasonal patterns.
- Original series were used for underemployment counts as seasonally adjusted counts by gender were not available.

