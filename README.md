# Tabular Machine Learning versus Physics-Based Baselines for Uncertainty-Aware Motion Forecasting in Autonomous Driving

ADY201m – Fall 2026 – Group 7
Members: Hà Anh Kiệt (SE203665), Phan Trần Trọng Phúc (SE204441)
Supervisor: Lê Võ Minh Thư

## Overview
We forecast the straight-line displacement of 1,172 vehicles from the Waymo Open Motion Dataset (WOMD v1.2) 3 s and 8 s ahead from one forecast origin (t = 1.0 s). Five tuned tabular models (Ridge, Random Forest, HistGradientBoosting, LightGBM, XGBoost) are compared with three physical baselines (constant velocity, constant acceleration, CTRV) on a 30% scenario-disjoint holdout (355 vehicles, 316 scenarios). We add split conformal intervals (global, by motion state, locally weighted), a hard-error warning, SHAP, and two context experiments on WOMD v1.3.0 (traffic signals) and v1.3.1 (self-driving-car route).

## Notebooks
| Notebook | Content |
|---|---|
| Notebook_A_Waymo_Trajectory.ipynb | Sampling, cleaning, SQL features, single-origin table at step 10, WOMD v1.3.0 / v1.3.1 extensions |
| Notebook_C_Waymo_Data_EDA_SQL.ipynb | Data understanding, EDA and SQL queries (DuckDB) |
| Notebook_B_Waymo_Trajectory.ipynb | Scenario split, physical baselines, 5 tuned models, conformal intervals (global, by motion state, locally weighted), hard-error warning, SHAP, context experiments, six-origin check |
| Notebook_D_Waymo_Models_RQ2_RQ3.ipynb | Independent cross-check of Notebook B (23 reproduced values, 16 sensitivity checks) |

## Main results
- 3 s: constant acceleration has the lowest MAE (0.97 m); no tabular model beats it, even with six forecast origins per vehicle.
- 8 s: all tree models beat every physical baseline; the selected Random Forest lowers the constant-velocity error by 20.3% (its 11.9% gain over constant acceleration is not significant).
- Conformal intervals: 89.3% / 91.8% coverage overall but only 71.3% / 78.7% for moving vehicles; a radius per motion state reaches 95.9% / 98.4% at about twice the width.
- Context: route features lower the self-driving car's 8 s MAE by 4.8% (without the on-route count); traffic-signal counts give no reliable gain.

## Data
WOMD is distributed under the Waymo Open Dataset License (non-commercial use). The raw data are not included in this repository; download WOMD v1.2, v1.3.0 and v1.3.1 from https://waymo.com/open.
