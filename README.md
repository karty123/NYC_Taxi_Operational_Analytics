# NYC Taxi Operational Analytics

## Project Summary

This repository contains an operational and behavioral analysis of NYC Yellow Taxi trips. The goal is to move beyond raw volume metrics and measure system behavior, operational efficiency, and periods of instability using reproducible Python notebooks.

**Key focus:** temporal patterns, efficiency (duration / speed), and conservative anomaly detection to identify true operational stress.

## Why this project

- **Problem:** Understand how taxi operations behave over time and identify inefficiencies and abnormal behavior that are not visible from volume alone.
- **Audience:** data analysts, operations researchers, and portfolio reviewers interested in reproducible, interpretable analysis.

## What the project does (operations)

- **Ingest & validate data:** load raw Yellow Taxi records and build a clean, defensible dataset.
- **Derive metrics:** compute trip duration, average speed, and time-based features (hour, weekday, month).
- **Temporal analysis:** study hourly, daily and monthly behavior to find rhythms and variability.
- **Efficiency analysis:** evaluate distance-duration relationships, average speeds, and identify low-speed (inefficient) periods.
- **Anomaly detection:** aggregate to daily metrics and apply conservative statistical thresholds (z-score) to flag abnormal days for duration/speed.
- **Synthesize insights:** combine analyses to explain when and why inefficiencies occur.

## Project structure

```
NYC_Taxi_Operational_Analytics/
├── data/                  # raw and processed datasets
├── notebooks/             # analysis notebooks (run in order)
├── outputs/
│   ├── figures/           # saved charts used in reporting
│   └── tables/            # summary tables (CSV)
├── docs/                  # problem statement, notes, and insights
├── presentation/          # optional slides or pdf
├── requirements.txt
└── README.md
```

## Notebooks (what each does)

- **`01_data_understanding_cleaning.ipynb`** — load raw parquet files, inspect schema, clean invalid trips, and derive core features (duration, avg speed, time parts). Ensures a defensible analysis base.
- **`02_temporal_behavior_analysis.ipynb`** — analyze hourly/weekday/monthly patterns, measure variability, and compare weekday vs weekend behavior.
- **`03_operational_efficiency_analysis.ipynb`** — evaluate distance vs duration, analyze average speeds, identify congestion windows and low-speed concentration by hour.
- **`04_anomaly_insights_summary.ipynb`** — aggregate to daily metrics, compute baselines, apply z-score based anomaly detection for volume/duration/speed, and synthesize insights.

## Output highlights

- Key output tables are in `outputs/tables/` including `anomaly_comparison_summary.csv` and `daily_anomaly_metrics.csv`.
- Example summary (from `outputs/tables/anomaly_comparison_summary.csv`):
  - **Normal days:** Avg Duration ≈ 15.62 min, Avg Speed ≈ 20.53 km/h
  - **Anomalous days:** Avg Duration ≈ 363.28 min, Avg Speed ≈ 15.16 km/h
  (See `outputs/tables/daily_anomaly_metrics.csv` for per-day anomaly flags and metrics.)

## Key insights (concise)

- Temporal rhythm is strong — predictable peak/off-peak windows provide a baseline for anomaly detection.
- Duration variability is a stronger indicator of operational stress than trip volume.
- Efficiency breakdowns (low speeds) concentrate in specific hours rather than being uniform.
- Conservative anomaly detection finds few volume anomalies but more efficiency-related anomalies (duration/speed), supporting the hypothesis that instability shows up in performance rather than demand.

## Getting started

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Place raw data files in `data/raw/` (parquet or CSV as used in the notebooks).

3. Run notebooks in order in a Jupyter environment or VS Code:

   - `notebooks/01_data_understanding_cleaning.ipynb`
   - `notebooks/02_temporal_behavior_analysis.ipynb`
   - `notebooks/03_operational_efficiency_analysis.ipynb`
   - `notebooks/04_anomaly_insights_summary.ipynb`

## Where to look next (files)

- Problem definition: `docs/problem_statement.md`
- Methodology and step rationale: `docs/analysis_notes.md`
- Final insights summary: `docs/insights_summary.md`
- Output tables: `outputs/tables/anomaly_comparison_summary.csv`, `outputs/tables/daily_anomaly_metrics.csv`

## Notes and caveats

- Some anomalous daily metrics reflect very small daily trip counts or data quirks — the notebooks apply conservative filtering and thresholds and document these cases.
- This project emphasizes interpretability and defensible analysis rather than predictive modeling.

## License

Add your license information here.
