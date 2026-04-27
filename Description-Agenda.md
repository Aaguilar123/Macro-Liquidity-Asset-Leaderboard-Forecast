## Phase 1: Data Acquisition & Preprocessing (March 30 - April 5)
* **Infrastructure:** Initialize the GitHub Repository. (Note: All members must commit weekly to demonstrate collaborative contribution per the rubric).
* **Data Ingestion:** Develop a shared, reproducible script to pull daily volume data (Yahoo Finance) and monthly macroeconomic indicators (FRED API).
* **The Baseline:** Implement the shared baseline model (e.g., a Simple Moving Average forecast) that all advanced models must beat in the final evaluation.

## Phase 2: Joint Exploratory Data Analysis (April 6 – April 12)
* **Feature Engineering:** Smooth daily volume (21-day window), apply 1%/99% Winsorization, and compute the uniform target variable: **`3M Log-RVOL`**.
* **EDA Artifacts:** Generate the Time-Series Decomposition, KDE Distribution plots (proving fat-tails), and the Macro Sensitivity Heatmaps.
* **Validation Protocol:** Formally document the rigorous evaluation setup (Chronological Time-Series Split: Train 2015-2024 / Test 2025-2026) and primary metrics (MAE, RMSE).
* **The Output:** Export the finalized, clean `final_engineered_data.csv`.

## Phase 3: Individual Modeling Sprints (April 13 - April 26)
*Working in isolated notebooks, all members train their respective models on `final_engineered_data.csv` to predict the same `3M Log-RVOL` target.*
* **Member A (SARIMAX):** Focuses on seasonal trends and structural volume shifts, utilizing decomposition insights.
* **Member B (XGBoost):** Focuses on non-linear volume spikes and regime boundaries, utilizing KDE insights regarding fat tails.
* **Member C (LSTM):** Focuses on sequential dependency and volatility clustering, utilizing deep learning to capture market "long memory."

## Phase 4: Evaluation, Discussion & Submission (April 27 - May 8)
* **Performance Review:** Evaluate all three models on the exact same 2025-2026 test set. Compare MAE and RMSE against the established baseline.
* **Group Reflection:** Synthesize findings. Discuss model stability, computational trade-offs, and why specific architectures (e.g., Deep Learning vs. Tree-based) handled the non-linear liquidity data better.
* **Submission Formatting:** Ensure the repository contains the Joint EDA Notebook, the three Individual Modeling Notebooks, and the final synthesis report.
