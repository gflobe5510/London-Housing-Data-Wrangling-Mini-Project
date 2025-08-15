# London-Housing-Data-Wrangling-Mini-Project
Brief Demonstration of Data Wrangling

## Overview
This project focuses on cleaning, standardizing, and merging two datasets on London housing to create a single, analysis-ready dataset. The goal is to demonstrate data wrangling and cleansing skills, from identifying quality issues to producing a reproducible cleaning pipeline.
## Datasets
Both datasets are from the London Datastore (https://data.london.gov.uk/) and cover housing, crime, salary, and demographic statistics.
- housing_in_london_monthly_variables.csv  
  Monthly-level housing data, including average prices, houses sold, and crime counts.
- housing_in_london_yearly_variables.csv  
  Yearly-level socio-economic indicators, including salaries, recycling rates, population size, and housing counts.
## Methodology
The notebook follows a clear step-by-step process:
1. Load & Inspect Data – Read CSVs, inspect structure, and check data types.
2. Standardize Column Names – Convert to lowercase snake_case for consistency.
3. Fix Data Types – Convert `date` to datetime; convert numeric-looking strings to numeric.
4. Clean Categorical Data – Standardize `area` names (title case, strip whitespace).
5. Explore & Visualize Missing Values – Generate missingness heatmaps before cleaning.
6. Handle Missing Values – Median imputation for certain numeric columns; leave sparse columns (e.g., `no_of_crimes`) as NaN where imputation may bias results.
7. Outlier Detection – Flag potential outliers using the IQR method.
8. Merge Datasets – Merge monthly and yearly datasets on `(area, year)`.
9. Add Derived Features – `crime_rate_per_1k`, `price_to_mean_salary`.
10. Compare Before/After – Side-by-side samples of raw vs. cleaned data; missingness heatmaps after cleaning.
## Key Insights
- Large gaps exist in certain socio-economic indicators (`life_satisfaction`, `recycling_pct`).
- Crime data is sparse for some areas, especially before 2000.
- After cleaning, datasets are fully merged and ready for exploratory analysis or dashboarding.
## Project Structure
.
├── london_housing_wrangle.ipynb
├── london_housing_wrangle_no_comments.ipynb
├── housing_in_london_monthly_variables.csv
├── housing_in_london_yearly_variables.csv
├── london_housing_cleaned.csv
└── README.md
## How to Run
1. Clone the repository and place both CSV files in the same folder as the notebook.
2. Install dependencies:
   pip install pandas numpy matplotlib
   Open and run the notebook:
## Future Improvements
- Use interpolation for `no_of_crimes` where possible.
- Standardize area codes (`code`) across datasets for more robust merges.
- Add external datasets (e.g., interest rates, inflation) for enriched analysis.
- Create an interactive Tableau or Power BI dashboard.
## License
This project is for educational purposes. Original data © London Datastore (https://data.london.gov.uk/).

1. Clone the repository and place both CSV files in the same folder as the notebook.
2. Install dependencies:
