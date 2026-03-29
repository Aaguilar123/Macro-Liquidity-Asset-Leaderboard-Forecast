## Project: Macro-Liquidity & Asset Leaderboard Forecast (2015–2026)
# 1. The Mission: "The Horse Race"
We are building a forecasting engine that ranks 5 key assets based on Volume Share (Liquidity) and Relative Performance (Returns). The goal is to predict which asset "wins" the leaderboard when macro conditions shift.
The 5 Assets:
- Stocks(Growth/Tech): QQQ (Nasdaq 100)
- Stocks(Consumer Staples(: XLP (Defensive/Necessities)
- Gold: GLD (Safe Haven/Store of Value)
- Bitcoin: BTC (High-Beta/Digital Liquidity)
- The Dollar: UUP (Cash/Global Safety)
________________________________________
## 2. The 4 Macro Regimes (Ranking Triggers)
Regime	Fed Policy	CPI (Inflation)	Unemployment	Predicted #1 Rank
1. Reflation	Dovish (Cuts)	Moderate	Low (Falling)	BTC / QQQ
2. Stagflation	Hawkish (Hikes)	High (Rising)	High (Rising)	GLD / XLP
3. Deflation	Dovish (Panic)	Negative (Falling)	High (Surging)	UUP (Cash)
4. Policy Shock	Pivot (Uncertain)	Volatile	Fluctuating	UUP / GLD
________________________________________
## 3. Individual Modeling Tasks (40 Pts Each)
- Member A: The Liquidity Ranker (VAR - Vector Autoregression)
o	Focus: Volume Lead-Lag.
o	Goal: Prove if a change in Fed Liquidity ($WALCL$) or Unemployment pushes volume into defensive assets (XLP) before the price actually moves.
- Member B: The Shock Ranker (Prophet)
o	Focus: Event Seasonality (Policy Shocks).
o	Goal: Forecast how the 2026 Midterms and Fed Meeting weeks flip the rankings of the Dollar (UUP) vs. Risk assets.
- Member C: The Winner Predictor (Random Forest / XGBoost)
o	Focus: Regime Classification.
o	Goal: A Machine Learning model using CPI, Rates, and Unemployment to predict which asset will be the #1 Return Performer next month.
________________________________________
## 4. Shared "Money Flow" Dashboard (30 Pts Shared)
In our Joint Notebook, we will produce:
- The Rolling Leaderboard: A dynamic chart showing the 5 assets climbing and falling in rank over the last decade.
- Unemployment vs. Leadership: Visual proof that as UNRATE (Unemployment) rises, XLP (Staples) begins to outrank QQQ (Tech) in volume.
- Volume Concentration Heatmap: A map showing which assets are "crowded" (highest volume rank) during each of the 4 regimes.
________________________________________
## 5. Data Architecture
- Market Data (Daily): Yahoo Finance (QQQ, XLP, GLD, BTC-USD, UUP).
- Macro Data (Monthly/Weekly): FRED API ( CPIAUCSL, UNRATE, WALCL, FEDFUNDS).

