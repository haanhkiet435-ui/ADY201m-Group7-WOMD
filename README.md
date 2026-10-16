# Tabular Vehicle Displacement Forecasting with Conformal Intervals (WOMD)

ADY201m – Fall 2026 – Group 7
Members: Hà Anh Kiệt (SE203665), Phan Trần Trọng Phúc
Supervisor: Lê Võ Minh Thư

## Overview
We forecast vehicle displacement 3 s and 8 s ahead from one forecast origin
(t = 1.0 s) on the Waymo Open Motion Dataset (WOMD v1.2), compare tabular models
with physics baselines (CV, CA, CTRV) under a scenario-disjoint split, add split
conformal prediction intervals, and train an early-warning classifier.

## Notebooks
| Notebook | Content |
|---|---|
| Notebook_A_Waymo_Trajectory_revised_2.ipynb | Data loading, per-vehicle feature table at step 10 |
| Notebook_C_Waymo_Data_EDA_SQL_revised.ipynb | EDA and SQL queries (DuckDB) |
| Notebook_B_Waymo_Trajectory_revised.ipynb | Baselines, Ridge / Random Forest,
