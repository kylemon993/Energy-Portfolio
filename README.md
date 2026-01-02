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

## Day 4 — Power BI Prep Export + First Dashboard (1 hour)

- [x] Create notebook: `notebooks/03_powerbi_prep_and_exports.ipynb`
- [x] Ensure folders exist: `data/processed/` and `outputs/powerbi/`
- [x] Load cleaned dataset: `data/processed/uk_electricity_clean.csv`
- [x] Confirm data types:
  - [x] `dtm` is datetime
  - [x] `f` is numeric
- [x] Create Power BI helper columns in Python:
  - [x] `minute` (dtm floored to minute)
  - [x] `rolling_5min` (5-min rolling mean)
  - [x] `deviation_from_50` (`f - 50.0`)
  - [x] `out_of_band` flag (`f < 49.9 or f > 50.1`)
- [x] Export Power BI-ready CSV: `data/processed/uk_electricity_pbi.csv`
- [x] Build first Power BI report:
  - [x] Import `data/processed/uk_electricity_pbi.csv`
  - [x] Line chart: `dtm` vs `f`
  - [x] Line chart: `dtm` vs `rolling_5min`
  - [x] KPI cards: Avg `f`, Min `f`, Max `f`, Out-of-band count
  - [x] Add Date/Time slicer
- [x] Save Power BI file: `outputs/powerbi/day4_grid_frequency_report.pbix`
- [x] Add “Day 4 Notes” to README (what you built + 1–2 insights)
- [x] Commit + push: `Day 4: Power BI export + first dashboard`

## Day 5 — Feature Engineering + Aggregation + Lightweight Export (1 hour)

- [ ] Create notebook: `notebooks/04_day5_feature_engineering.ipynb`
- [ ] Confirm notebook is running from project root (print `Path.cwd()`)

- [ ] Load Power BI-ready dataset:
  - [ ] Read: `Data/Processed/uk_electricity_pbi.csv` (or your current processed path)
  - [ ] Confirm: `df.shape`, `df.head()`, `df.dtypes`

- [ ] Data quality checks:
  - [ ] Check datetime coverage: min/max of `dtm`
  - [ ] Check duplicates on `dtm`
  - [ ] Confirm frequency column is numeric (`f` or `Frequency (Hz)`)

- [ ] Feature engineering (time-based):
  - [ ] Create: `hour`, `day_of_week`, `day_name`, `is_weekend`
  - [ ] Create: `deviation_from_50` (frequency - 50.0)
  - [ ] Create: `out_of_band` flag (e.g., <49.8 or >50.2)

- [ ] Aggregation to reduce file size (key deliverable):
  - [ ] Set datetime index and sort by time
  - [ ] Create 1-minute dataset with:
    - [ ] `f_mean`, `f_min`, `f_max`, `f_std`
    - [ ] `out_of_band_count` per minute
  - [ ] Export: `Data/Processed/uk_electricity_1min.csv`

- [ ] Optional exports (choose 1):
  - [ ] Export 5-minute dataset: `Data/Processed/uk_electricity_5min.csv`
  - [ ] Export 15-minute dataset: `Data/Processed/uk_electricity_15min.csv`

- [ ] Power BI refresh:
  - [ ] Point Power BI to `uk_electricity_1min.csv`
  - [ ] Refresh visuals and confirm slicer responsiveness

- [ ] Add “Day 5 Notes” section to README:
  - [ ] What you built (aggregation + features)
  - [ ] Before vs after row count + file size
  - [ ] 1–2 insights from distribution or out-of-band counts

- [ ] Commit + push: `Day 5: feature engineering + 1-min aggregated export`
