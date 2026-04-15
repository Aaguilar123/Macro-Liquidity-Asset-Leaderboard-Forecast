## Project: Macro-Liquidity & Asset Flow Forecast (2015–2026)

# 1. The Mission: "The Liquidity Horse Race"
We are building a forecasting engine that ranks 5 key assets based exclusively on **Volume Share (Liquidity Concentration)**. The goal is to predict which asset "wins" the market's attention when macro conditions shift. We are tracking **Capital Migration**—proving that where the money flows, the regime follows.

The 5 Assets:
- BTC-USD: Speculative Liquidity (High-Beta/Digital Risk)
- QQQ: Growth/Tech Liquidity (Equity Expansion)
- GLD: Store of Value Liquidity (Inflation Hedge)
- XLP: Defensive/Necessity Liquidity (Safety/Staples)
- UUP: Global Cash Liquidity (The Safety Valve)

---

# 2. The 4 Macro Regimes (Liquidity Ranking Triggers)

| Regime | Fed Policy | CPI (Inflation) | Unemployment | Liquidity Winner (#1) |
| :--- | :--- | :--- | :--- | :--- |
| 1. Expansion | Dovish (Cuts) | Moderate | Low (Falling) | BTC / QQQ |
| 2. Inflationary | Hawkish (Hikes) | High (Rising) | Low (Stable) | GLD / BTC |
| 3. Contraction | Dovish (Panic) | Falling | High (Rising) | UUP / XLP |
| 4. Policy Shock | Pivot (Uncertain) | Volatile | Fluctuating | UUP / GLD |

---

# 3. Individual Modeling Tasks (40 Pts Each)

- **Member A: The Liquidity Flow Ranker (VAR - Vector Autoregression)**
  - **Focus**: Macro Lead-Lag on Volume Share.
  - **Goal**: Prove if a spike in Unemployment or a change in Fed Rates causes a statistically significant shift in **Volume Share** from Tech (QQQ) to Staples (XLP) before the price trend fully realizes.

- **Member B: The Liquidity Seasonality Ranker (Prophet)**
  - **Focus**: Event-Driven Volume Shocks.
  - **Goal**: Forecast how the 2026 Midterms and Fed Meeting weeks flip the concentration of **Volume Share** between the Dollar (UUP) and Risk assets.

- **Member C: The Flow Classifier (Random Forest / XGBoost)**
  - **Focus**: Regime-Based Volume Winner.
  - **Goal**: A Machine Learning model using CPI, Rates, and Unemployment to predict which asset will capture the **Highest Volume Share** (The Winner) next month.

---

# 4. Shared "Money Flow" Dashboard (30 Pts Shared)

In our Joint Notebook, we will produce:
- **The Volume Leaderboard**: A dynamic chart showing the 5 assets climbing and falling in rank based on **Volume Share** over the last decade.
- **Unemployment vs. Defensive Flow**: Visual proof that as UNRATE rises, **XLP (Staples)** begins to outrank **QQQ (Tech)** in total **Volume Share** concentration.
- **Volume Concentration Heatmap**: A map showing which assets hold the highest **Volume Share** rank during each of the 4 specific macro regimes.

---

# 5. Data Architecture

- **Market Data (Daily)**: Yahoo Finance Volume (QQQ, XLP, GLD, BTC-USD, UUP). Used to calculate % Volume Share.
- **Macro Data (Monthly)**: FRED API (CPIAUCSL - Inflation, UNRATE - Unemployment, FEDFUNDS - Interest Rates).
