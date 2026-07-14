# Investments & Portfolio Management — Project 1

A multi-stock portfolio analysis project covering time series analysis, descriptive statistics, index construction, minimum variance portfolio optimisation, and pre/post-Covid structural break analysis across five securities over a 6-year period (January 2018 – December 2023).

---

## Project Structure

```
IPM/
├── Project1_Group03.pdf     # Full report with all tables and interpretations
└── README.md
```

**Securities analysed:** Exxon (XOM), Shell (SHEL), JPMorgan (JPM), Wells Fargo (WFC), SPY ETF
**Period:** January 2018 – December 2023 (72 monthly observations)
**Tools:** Minitab

---

## Section 1 — Descriptive Analysis & Index Construction

### Time Series Analysis

All five securities share a common structural break at observations 28–35 (2020), corresponding to the Covid-19 market shock. Key observations:

- Energy stocks (XOM, SHEL) crashed and recovered symmetrically — the clearest V-shape
- WFC had the sharpest drop among financials and the weakest post-Covid recovery
- SPY showed the smoothest and strongest recovery of all five series
- Return series fluctuate around zero with no trend, but volatility clusters visibly around the 2020 shock

### Descriptive Statistics

| Security | Arithmetic Mean | Geometric Mean | Std Deviation |
|---|---|---|---|
| SPY | 0.8756% | 0.3395% | 5.2546% |
| JPM | 0.8410% | 0.5787% | 7.7387% |
| XOM | 0.6425% | 0.5716% | 9.6030% |
| WFC | 0.5340% | 0.2432% | 9.5657% |
| SHEL | 0.2107% | 0.2350% | 7.9110% |

SPY dominates on both return and risk — highest mean, lowest standard deviation. This is the diversification premium of the broad market over individual stocks made explicit.

### Index Construction — Three Methods Compared

| Index Type | Arithmetic Mean | Std Deviation | Key Characteristic |
|---|---|---|---|
| Price-Weighted | 0.4438% | 0.2789% | Lowest volatility; driven by stock price, not market cap |
| Value-Weighted | 2.9360% | 25.2325% | Highest return AND highest risk; large-cap dominated |
| Equal-Weighted | 0.4371% | 7.5707% | Balanced exposure; moderate return and risk |

The value-weighted index best represents true market behaviour — it is the structure used by S&P 500, FTSE, and NIKKEI — but at the cost of concentrated large-cap risk.

### Correlation Matrix

| | XOM | WFC | JPM | SHEL |
|---|---|---|---|---|
| XOM | — | 0.651 | 0.570 | **0.770** |
| WFC | 0.651 | — | **0.789** | 0.655 |
| JPM | 0.570 | 0.789 | — | 0.601 |
| SHEL | 0.770 | 0.655 | 0.601 | — |

Within-industry correlations are consistently higher (XOM–SHEL: 0.770, WFC–JPM: 0.789) than cross-industry pairs — confirming that sector-level common factors drive co-movement more than macro factors alone.

---

## Section 2 — Minimum Variance Portfolio (MVP) Construction

### Pair 1: Exxon & Shell (Same Sector)

| Stock | Weight | Avg Return | Std Dev | Sharpe |
|---|---|---|---|---|
| Exxon | 10.77% | 0.643% | 9.60% | 0.0515 |
| Shell | 89.23% | 0.211% | 7.91% | 0.0079 |
| **MVP** | — | **0.257%** | **7.88%** | **0.0138** |

Portfolio risk (7.88%) drops only marginally below Shell's standalone risk (7.91%) — limited diversification benefit from combining two oil stocks with high correlation.

### Pair 2: Exxon & JPMorgan (Cross-Sector)

| Stock | Weight | Avg Return | Std Dev | Sharpe |
|---|---|---|---|---|
| Exxon | 26.01% | 0.643% | 9.60% | 0.0515 |
| JPM | 73.99% | 0.841% | 7.74% | 0.0895 |
| **MVP** | — | **0.789%** | **7.44%** | **0.0862** |

Risk falls more meaningfully to 7.44% and Sharpe improves 6× vs. the Exxon-Shell MVP — demonstrating that **cross-industry diversification generates materially better risk-adjusted outcomes than within-industry diversification**.

---

## Section 3 — Pre/Post-Covid Structural Break Analysis

### Exxon & Shell — How Covid Changed Optimal Weights

| Period | Exxon Weight | Shell Weight |
|---|---|---|
| Pre-Covid (2018–2019) | 27.08% | 72.92% |
| Post-Covid (2021–2023) | **–30.08%** | **130.08%** |

The model shifts to a **short position in Exxon** post-Covid. After 2020, XOM and SHEL began moving much more similarly (higher correlation), eliminating diversification benefit. To maintain minimum variance, the optimiser requires shorting one asset to offset the now-correlated long. This demonstrates how structural events can fundamentally alter optimal portfolio weights.

### Market Regression — All Four Stocks

| Stock | Alpha | Beta | R² |
|---|---|---|---|
| Exxon | 0.0073 (insig.) | –0.234 (insig.) | 1.62% |
| Shell | 0.00134 (insig.) | –0.081 (insig.) | 0.29% |
| JPM | 0.00736 (insig.) | –0.195 (insig.) | 1.77% |
| WFC | –0.0010 (insig.) | –0.169 (insig.) | 0.86% |

All R² values below 2% — the broad market explains almost none of the return variation for these stocks over this period. Returns are driven primarily by firm-specific and sector-specific factors, not systematic market risk.

### Wells Fargo & Shell — Least Market-Dependent Pair

| Stock | Weight | Avg Return | Std Dev | Sharpe |
|---|---|---|---|---|
| WFC | 24.34% | –0.094% | 9.55% | –0.0249 |
| Shell | 75.66% | 0.214% | 7.97% | 0.0087 |
| **MVP** | — | **0.139%** | **7.76%** | **–0.0007** |

Risk reduces through combination, but the portfolio Sharpe remains near zero. Low market correlation alone does not guarantee good risk-adjusted returns — the underlying return quality of the assets still determines the outcome.

---

## Key Findings

| Finding | Implication |
|---|---|
| SPY outperforms all individual stocks on both return and risk | Diversification premium is real and large |
| Within-industry correlation consistently exceeds cross-industry | Sector selection matters as much as stock selection |
| Cross-sector MVP (XOM–JPM) Sharpe is 6× higher than same-sector MVP (XOM–SHEL) | Industry diversification is not optional |
| Post-Covid optimal weights included a short position in Exxon | Correlation is not stable — weights must be recalibrated after structural breaks |
| All four stocks show near-zero R² vs. the broad market | Idiosyncratic risk dominates over systematic risk for these securities in this period |
| Low beta ≠ good Sharpe | Risk reduction without return improvement produces near-zero or negative Sharpe ratios |

---

## Skills Demonstrated

| Area | Techniques |
|---|---|
| Portfolio Theory | Minimum variance portfolio construction, Sharpe ratio optimisation, diversification analysis |
| Statistical Analysis | Arithmetic vs. geometric mean, standard deviation, correlation matrix |
| Index Construction | Price-weighted, value-weighted, and equal-weighted methodologies |
| Regression Analysis | Alpha/beta estimation, R² interpretation, statistical significance (p-values) |
| Event Analysis | Pre/post-Covid structural break comparison, dynamic weight recalibration |

---

*Completed as part of the Investments & Portfolio Management course. Tools used: Microsoft Excel, Minitab.*
