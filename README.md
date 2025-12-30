# Energy Analyst Portfolio (Training)

## Project goal
Build job-ready data analyst skills using UK electricity data, with a focus on:
- VS Code workflow
- Python (basic pandas + charts)
- SQL (core interview skills)
- Power BI (Power Query + DAX + dashboarding)

## Datasets used
Public UK electricity datasets (to be linked/credited per project):
- Generation mix / demand-style time series
- System price-style time series

## Tools
- VS Code
- Python
- SQL
- Power BI
- Git/GitHub

## Project structure
- data/
  - raw/         (original datasets)
  - processed/   (cleaned datasets created by notebooks/scripts)
- notebooks/     (analysis notebooks)
- src/           (python scripts/functions)
- outputs/
  - figures/     (charts exported as PNG)
  - tables/      (summary tables exported as CSV)

## Progress log
### Day 1
- [x] Created project structure
- [x] Created README.md and .gitignore
- [x] Initialized git repo and pushed to GitHub

### Day 2
- [x] Set up Python environment
- [x] Ran first notebook
- [x] Loaded dataset and performed initial checks

## Day 3 — UK Electricity Dataset: First Look + Clean + Chart (1 hour)

- [x] Create folders (if missing): `data/raw/`, `data/processed/`, `outputs/figures/`, `outputs/tables/`
- [x] Download 1 UK electricity CSV dataset (demand or generation mix)
- [x] Save dataset to `data/raw/` and rename to `uk_electricity.csv`
- [x] Create notebook: `notebooks/02_uk_electricity_first_look.ipynb`
- [x] In the notebook: load the CSV and confirm `df.shape` + `df.head()`
- [x] Inspect structure: run `df.info()` + missing values summary
- [x] Standardise column names (lowercase, underscores)
- [x] Identify the datetime column and convert it using `pd.to_datetime(...)`
- [x] Sort by datetime and drop rows where datetime is missing
- [x] Choose 1 main metric column (e.g., demand / load / generation / wind / solar)
- [x] Create 1 time-series chart for the main metric
- [x] Save the chart to `outputs/figures/day3_timeseries.png`
- [x] Export cleaned data to `data/processed/uk_electricity_clean.csv` (for Power BI later)
- [x] Add a short “Day 3 Notes” section to README:
  - [x] Dataset name + source
  - [x] Rows/columns
  - [x] Cleaning steps performed
  - [x] 1–2 quick observations
- [x] Commit + push: `Day 3: first dataset + cleaning + chart`
