# Analysis Notes

# Analysis Notes & Methodology  
**Project:** Operational & Behavioral Analysis of NYC Taxi Trips using Python

---

## Purpose of This Document

This document explains the **analytical thinking and methodology** behind the notebooks used in this project.  
It connects **business questions to analytical steps**, ensuring transparency, interpretability, and reproducibility.

The notebooks serve as **evidence** of analysis execution, while this document explains **why each step was necessary**.

---

## Notebook 01: Data Understanding & Cleaning  
**File:** `01_data_understanding_cleaning.ipynb`

### Objective
Establish a **clean, defensible analytical foundation** before any interpretation or insight generation.

### Key Analytical Steps
- Loaded raw NYC Yellow Taxi trip data from parquet files
- Inspected schema, data types, missing values, and time coverage
- Reduced scope to operationally relevant columns
- Converted pickup and dropoff timestamps to datetime format
- Derived core behavioral metrics:
  - Trip duration (minutes)
  - Average speed (km/h)
  - Time-based features (hour, weekday, month)
- Applied strict validity rules:
  - Removed trips with zero/negative duration
  - Removed unrealistic trip distances
  - Filtered implausible average speeds

### Why This Matters
All downstream insights rely on **trustworthy data**.  
This notebook ensures:
- anomalies are not artifacts of bad data
- variability reflects real system behavior
- later conclusions are analytically defensible

---

## Notebook 02: Temporal Behavior Analysis  
**File:** `02_temporal_behavior_analysis.ipynb`

### Objective
Understand **how taxi operations behave over time**, rather than how much activity occurs.

### Key Analytical Steps
- Verified temporal coverage of the cleaned dataset
- Analyzed hourly demand distribution to identify peak and off-peak periods
- Compared weekday vs weekend behavior
- Examined monthly trip trends to understand seasonality
- Studied how average trip duration varies by hour
- Measured variability (standard deviation) of trip duration across time windows

### Why This Matters
Temporal patterns reveal:
- system rhythm
- predictable vs unstable operating periods
- early indicators of congestion and stress

This analysis moves beyond raw volume to understand **behavioral dynamics**.

---

## Notebook 03: Operational Efficiency Analysis  
**File:** `03_operational_efficiency_analysis.ipynb`

### Objective
Evaluate **how efficiently the taxi system operates**, independent of demand levels.

### Key Analytical Steps
- Analyzed the relationship between trip distance and trip duration
- Examined distribution of average taxi speeds
- Identified congestion windows through speed drops by hour
- Defined inefficiency using low-speed thresholds (bottom decile)
- Analyzed concentration of slow trips across time periods
- Measured speed variability to distinguish stable vs unstable operating hours

### Why This Matters
Efficiency breakdowns often occur **without demand spikes**.  
This notebook demonstrates that:
- congestion manifests as variability before volume increases
- average metrics alone can hide instability
- operational inefficiency is unevenly distributed over time

---

## Notebook 04: Anomaly Detection & Insight Synthesis  
**File:** `04_anomaly_insights_summary.ipynb`

### Objective
Identify **abnormal system behavior** and synthesize insights across all analyses.

### Key Analytical Steps
- Aggregated trip data to daily-level metrics
- Computed statistical baselines for:
  - daily trip volume
  - average trip duration
  - average speed
- Applied conservative z-score thresholds to detect anomalies
- Identified days with:
  - abnormal duration
  - abnormal speed
  - combined instability
- Compared anomalous days to normal days to characterize differences

### Why This Matters
This notebook demonstrates:
- disciplined anomaly detection (not forcing results)
- separation of normal variability from true instability
- ability to synthesize insights across multiple dimensions

Empty anomaly results for volume were treated as **valid findings**, reinforcing analytical integrity.

---

## Overall Analytical Flow

1. **Clean the data** → ensure trust
2. **Understand temporal behavior** → identify rhythm and variability
3. **Evaluate efficiency** → detect hidden congestion and instability
4. **Detect anomalies** → isolate abnormal system behavior
5. **Synthesize insights** → explain why patterns occur

This flow mirrors **real-world analytics practice**, not academic exercises.

---

## Positioning Note

The analysis prioritizes:
- interpretability over complexity
- reasoning over dashboards
- operational understanding over financial metrics

This makes the project directly relevant to **data analyst and operations analytics roles**.

---
