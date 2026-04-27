# Macro-Driven Asset Volume Forecasting (2015–2026)

## 1. Project Objective
This project builds predictive models to forecast **3-Month Relative Volume Growth (3M Log-RVOL)** across 5 asset classes. Rather than predicting price action, the goal is to analyze how macroeconomic regimes influence forward changes in trading activity and asset allocation. 

Our Exploratory Data Analysis (EDA) indicates that market volume is non-linear and exhibits fat-tailed distributions. To address this, our team evaluates three distinct modeling architectures (Classical, Tree-Based, and Deep Learning) against a standardized target variable.

**Tracked Assets:**
* **`BTC-USD`**: High-Beta / Digital Risk
* **`QQQ`**: Broad Equity / Tech Growth
* **`GLD`**: Inflation Hedge / Store of Value
* **`XLP`**: Defensive Equities / Staples
* **`UUP`**: US Dollar / Cash Proxy

---

## 2. Macro Sensitivities (Key EDA Findings)
Our structural analysis identified clear, regime-dependent volume triggers. These relationships inform our feature engineering and modeling choices:

* **Fed Funds Rate (`QQQ`)**: Tech volume is relatively resilient to rate changes, showing only a slight rightward distribution shift during easing cycles.
* **CPI Inflation (`BTC-USD`)**: Displays a negative correlation. Right-tail volume surges (high trading activity) occur predominantly during periods of disinflation.
* **Unemployment (`UUP`, `XLP`, `GLD`)**: Serves as the primary driver for defensive rotation. Rising unemployment triggers structural volume shifts out of risk assets and into safety.

---

## 3. Individual Modeling Tasks 
*To satisfy the project rubric and ensure a valid comparative discussion, all three models perform a regression task predicting the exact same target: **`3M Log-RVOL`**.*

**Member A: Structural Baseline (SARIMAX)**
* **Focus**: Seasonal and Autoregressive Trends.
* **Methodology**: Utilizes the 252-trading-day annual seasonality proven in our time-series decomposition to model baseline volume shifts while absorbing exogenous macro indicators.

**Member B: Non-Linear Regime Analysis (XGBoost Regressor)**
* **Focus**: Distribution Tails and Regime Boundaries.
* **Methodology**: Leverages macro state regimes (e.g., Rising vs. Falling CPI) to predict non-linear volume spikes that classical statistical models fail to capture.

**Member C: Sequential Dependency (LSTM)**
* **Focus**: Volatility Clustering and Sequence Memory.
* **Methodology**: Evaluates how consecutive months of shifting macro conditions compound over time to influence delayed volume changes, utilizing Recurrent Neural Networks to handle sequential dependency.

---

## 4. Shared Data Architecture & Artifacts 
All models are trained on `final_engineered_data.csv`, generated through our joint EDA pipeline.

**Core EDA Artifacts:**
* **Time-Series Decomposition**: Justified SARIMAX by isolating structural trends and rigid annual seasonality.
* **KDE Distributions**: Demonstrated non-Gaussian, fat-tailed asset behavior.
* **Data Preprocessing**: Smoothed daily volume, applied 1%/99% Winsorization to cap extreme statistical noise, and generated the forward-looking `3M Log-RVOL` targets to strictly prevent data leakage.

---

## 5. Evaluation & Validation Framework
To ensure an academically rigorous comparison, the group utilizes a standardized evaluation pipeline.

* **Validation Split**: Strict Chronological Time-Series Split (No random shuffling).
  * **Training Set**: Jan 2015 – Dec 2024 (~10 Years)
  * **Testing Set**: Jan 2025 – Present (~1.5 Years)
* **Primary Metric**: **MAE (Mean Absolute Error)** — Selected for robustness against extreme outliers and fat-tail volume shocks.
* **Secondary Metric**: **RMSE (Root Mean Square Error)** — Utilized to measure the penalty for missing significant regime-driven volume shifts.
