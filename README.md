# NYC Taxi Operational Analytics

## Project Overview

This project analyzes NYC taxi operational data to understand temporal behavior, operational efficiency, and identify anomalies.

## Project Structure

```
NYC_Taxi_Operational_Analytics/
│
├── data/
│   ├── raw/                # original downloaded files (unchanged)
│   ├── processed/          # cleaned / filtered datasets
│
├── notebooks/
│   ├── 01_data_understanding_cleaning.ipynb
│   ├── 02_temporal_behavior_analysis.ipynb
│   ├── 03_operational_efficiency_analysis.ipynb
│   ├── 04_anomaly_insights_summary.ipynb
│
├── outputs/
│   ├── figures/            # saved charts used in report/presentation
│   ├── tables/             # summary tables (CSV)
│
├── docs/
│   ├── problem_statement.md
│   ├── analysis_notes.md
│   ├── insights_summary.md
│
├── presentation/
│   └── nyc_taxi_operational_analysis.pdf (optional but good)
│
├── requirements.txt
├── README.md
```

## Getting Started

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Place raw data files in `data/raw/`

3. Run notebooks in order:
   - 01_data_understanding_cleaning.ipynb
   - 02_temporal_behavior_analysis.ipynb
   - 03_operational_efficiency_analysis.ipynb
   - 04_anomaly_insights_summary.ipynb

## License

Add your license information here.
