# Chicago-Crime-Dataset-Capstone
Full stack data analytics capstone analyzing Chicago crime data, built with BigQuery SQL, Python EDA, a Random Forest arrest prediction model, and a 6 page interactive Power BI dashboard.

## Overview

This project analyzes the Chicago Crime dataset using BigQuery, Python, and Power BI. It covers the full pipeline from raw data exploration to a final multi-page interactive dashboard, including a Random Forest model predicting arrest likelihood.

## Project Structure

```
├── chicago_crime_eda.ipynb       # Main EDA notebook (BigQuery + Python)
├── chicago_crime_theme.json      # Power BI custom theme file
├── feature_importance.csv        # Exported ML model feature importances
├── dashboard_screenshots.pdf     # Screenshots of all 6 Power BI dashboard pages
└── README.md                     # This file
```

## Tools Used

- **Google BigQuery** — data storage, SQL aggregation queries
- **Google Colab / Python** — data cleaning, feature engineering, EDA, visualizations, machine learning
- **Power BI Desktop** — final interactive dashboard

## Setup Instructions

### 1. BigQuery Connection

The notebook connects to a BigQuery project. Before running, update this value near the top of the notebook to match your own project:

```python
PROJECT_ID = "your-project-id-here"
```

The main dataset is expected at:
```
your-project-id.main_data.chicago_crime_sample
```

If you're using a different dataset or table name, update the SQL queries in **Section 2 — SQL Data Acquisition** accordingly.

### 2. Running the Notebook

Open `chicago_crime_eda.ipynb` in Google Colab. Run all cells top to bottom — the notebook will:

1. Authenticate with BigQuery (you'll be prompted to log in)
2. Pull and clean the data
3. Engineer time-based features (hour, month, season, etc.)
4. Run the full EDA with visualizations
5. Train the Random Forest arrest prediction model
6. Export the cleaned dataset and feature importance results back to BigQuery

No manual edits are needed beyond the `PROJECT_ID` at the top, unless your table names differ.

### 3. Power BI Dashboard

Since the `.pbix` file is too large for GitHub, the final dashboard is provided as `dashboard_screenshots.pdf`, a screenshot of each of the 6 dashboard pages. The PDF reflects the same dark themed, multi page report built from the cleaned data exported in Step 2, with Year, Crime Type, and District slicers synced across all pages so filtering on one page updates the rest.

**Dashboard pages:**

| Page | Content |
|---|---|
| 1 — Overview | KPI cards, year-over-year crime trend |
| 2 — When | Hour, day-of-week, and monthly/seasonal patterns |
| 3 — What | Crime type breakdown and arrest rate by crime type |
| 4 — Where | District breakdown, geographic map, location types |
| 5 — Arrests | Arrest rate over time, domestic vs non-domestic, feature importance |
| 6 — Conclusions | Written findings and summary visuals |

## Key Findings

See **Section 9 — Findings & Analytical Conclusions** in the notebook, or Page 6 of `dashboard_screenshots.pdf`, for the full written summary. Highlights include a long-term decline in crime volume, a significant gap between theft's prevalence and its arrest rate, and crime type being the strongest predictor of arrest likelihood in the machine learning model.

## Author

Amon Santos — Data Analytics Capstone, Mountainland Technical College (MTECH)
