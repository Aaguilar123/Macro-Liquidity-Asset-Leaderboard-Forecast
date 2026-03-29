## Phase 1: The Foundation (March 30 - April 5)
- Infrastructure: Set up a GitHub Repository. Ensure every member commits at least once a week to prove "active collaboration" (as required by the rubric).
- Data Pull: Create a shared script to pull Yahoo Finance (Prices/Volume) and FRED API (Macro indicators).
- The Baseline: Agree on a Naive Forecast (e.g., "Next month = This month") that everyone must use to compare their models against.
## Phase 2: The Joint Notebook (April 6 – April 12)
- The Regime Mapper: Build a function that labels every month from 2015–2026 as one of your 4 Macro Regimes.
- EDA: Visualize the "Horse Race." Create a line chart showing the total returns of the 5 assets.
- The Strategy: Formally document your Validation Setup. (Recommendation: Use a 80/20 train-test split or a rolling-window approach).
## Phase 3: The Individual Sprints (April 13 - 26)
Each member works in their own individual notebook using the same cleaned data:
- Member A	Liquidity	VAR	Does Fed Policy change predict $XLP$ volume?
- Member B	Seasonality	Prophet	How do Fed Meetings/Elections flip the Leaderboard?
- Member C	Classification	XGBoost	Predict which asset will be #1 next month.
## Phase 4: The Final Polish (April 27 - May 8 & Submission)
- The Reflection: Meet as a group to discuss why results differ. (e.g., "Why did Member C's XGBoost outperform Member A's VAR?").
- The Dashboard: Combine individual outputs into the Volume Heatmap and Leaderboard Forecast.
- Submission: Ensure everyone submits two files (the Joint Notebook + their Individual Notebook).

