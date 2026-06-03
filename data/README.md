# Data

- **care_state.csv**: CMS "Timely and Effective Care" measures reported at the U.S. state/territory level, sourced from [data.cms.gov](https://data.cms.gov) and curated for [TidyTuesday 2025-04-08 (week 14)](https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-04-08). 1,232 rows × 8 columns covering 56 jurisdictions and 22 measures across 6 condition areas, for 2023–2024 reporting periods.
- **state_population.csv**: 2024 state population estimates (U.S. Census Bureau Vintage 2024 estimates), used to contextualize Question 1. 51 rows (50 states + DC).

# Codebook for `care_state.csv`

## Variable Names and Descriptions:

- **state**: Two-letter postal code for the state, district, or territory.
- **condition**: Care/condition area the measure belongs to (Emergency Department, Sepsis Care, Healthcare Personnel Vaccination, Cataract surgery outcome, Colonoscopy care, Electronic Clinical Quality Measure).
- **measure_id**: Short unique identifier for the measure (e.g., `OP_18b`, `OP_23`, `SEP_1`).
- **measure_name**: Full human-readable description of the measure, often noting whether higher or lower scores are better.
- **score**: The measured value. Units depend on the measure, minutes for ED-timing measures (e.g., `OP_18b`) and percentages for rate measures (e.g., `OP_23`, `IMM_3`). May be `NA` where data are unavailable.
- **footnote**: Footnote codes describing data-availability or data-source caveats; `NA` when none apply.
- **start_date**: Start of the measurement/reporting period (date).
- **end_date**: End of the measurement/reporting period (date).

## Data Types:

- **state**: character
- **condition**: character
- **measure_id**: character
- **measure_name**: character
- **score**: double (numeric)
- **footnote**: character
- **start_date**: date
- **end_date**: date

## Measures used in this project

- **OP_18b** and **OP_18b_LOW_MIN / OP_18b_MEDIUM_MIN / OP_18b_HIGH_MIN / OP_18b_VERY_HIGH_MIN**: Median time (minutes) patients spent in the emergency department before leaving, overall and stratified by ED patient-volume tier. Lower is better. *(Question 1)*
- **OP_23**: Percentage of stroke patients who received head CT/MRI interpretation within 45 minutes of arrival. Higher is better. *(Question 2)*
- **OP_29**: Percentage of colonoscopy patients with appropriate follow-up interval recommendations. Higher is better. *(Question 2)*
- **SAFE_USE_OF_OPIOIDS**: Safe use of opioids, concurrent prescribing measure (direction to be confirmed from `measure_name`). *(Question 2)*

# Codebook for `state_population.csv`

## Variable Names and Descriptions:

- **state**: Two-letter postal code (joins to `care_state.csv`).
- **state_name**: Full state/district name.
- **population**: 2024 population estimate (count of people).

## Data Types:

- **state**: character
- **state_name**: character
- **population**: double (numeric)
