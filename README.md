# Investments & Portfolio Management

A two-project repository covering equity analysis, portfolio optimisation, asset pricing model estimation, and risk decomposition across multiple securities and time periods.

---

## Repository Structure

```
Investments-Portfolio-Management/
│
├── Project-1/
│   ├── Project1_Group03.pdf     # Full report
│   └── README.md
│
└── Project-2/
    ├── IPM_Assignment_2.pdf     # Full report
    └── README.md
```

---

## Projects

### Project 1 — Multi-Stock Portfolio Analysis & Index Construction
> Time Series · Descriptive Statistics · Index Construction · Minimum Variance Portfolio · Pre/Post-Covid Structural Break

Analyses five securities (XOM, SHEL, JPM, WFC, SPY) over 72 monthly observations from January 2018 to December 2023. Builds three custom indices (price-weighted, value-weighted, equal-weighted) and constructs minimum variance portfolios across multiple stock pairs — including a pre/post-Covid comparison that demonstrates how rising correlation forces short positions into an otherwise long-only portfolio.

**Key results:**
- SPY dominates all individual stocks on both return (0.876%) and risk (5.25% σ) — the diversification premium quantified
- Cross-sector MVP (XOM–JPM) Sharpe ratio is 6× higher than same-sector MVP (XOM–SHEL)
- Post-Covid optimal weights for XOM–SHEL include a –30% short in Exxon, driven by correlation convergence
- All four stocks show R² < 2% vs. the broad market — returns are idiosyncratic, not systematic, in this period

→ [`Project-1/`](./Project-1/)

---

### Project 2 — CAPM, Fama-French & Index Model Estimation
> Portfolio Optimisation · CAPM · Fama-French Three-Factor Model · Sector Index Model · Risk Decomposition

Analyses Target (TGT) and Walmart (WMT) using three asset pricing frameworks — CAPM, Fama-French three-factor model, and a sector index model using the SPDR S&P Retail ETF (XRT) as benchmark. Compares optimal risky portfolios constructed under each model's expected returns, and explains why model-based portfolios are more reliable than historically-fitted ones.

**Key results:**
- TGT beta ≈ 1.012 (cyclical retailer); WMT beta = 0.428 (defensive, recession-resistant)
- Neither stock generates statistically significant alpha under CAPM or Fama-French
- Historical Sharpe (0.1937) vs. CAPM Sharpe (0.059) — gap explained by sample overfitting, not genuine alpha
- Index model R² for TGT vs. XRT (0.3232) exceeds CAPM R² (0.2856) — sector benchmark explains more return variation than the broad market
- WMT shows an anomalous SMB loading (0.533) despite being a mega-cap — a structural retail sector effect

→ [`Project-2/`](./Project-2/)

---

## Skills Demonstrated Across Both Projects

| Area | Techniques |
|---|---|
| Portfolio Theory | Minimum variance optimisation, Sharpe ratio maximisation, mean-variance frontier |
| Asset Pricing | CAPM, Fama-French three-factor model, sector index model |
| Risk Analysis | Systematic vs. idiosyncratic variance decomposition, Information Ratio, beta interpretation |
| Index Construction | Price-weighted, value-weighted, equal-weighted methodologies and trade-offs |
| Statistical Analysis | OLS regression, p-value interpretation, R², correlation matrix, arithmetic vs. geometric mean |
| Event Analysis | Pre/post-Covid structural break analysis, dynamic weight recalibration |

---

## Connecting Theme

Both projects arrive at the same underlying conclusion from different angles: **the benchmark you choose fundamentally changes what risk means**. Project 1 shows this through index construction — how weighting methodology changes what the "market" looks like. Project 2 shows it through model selection — a stock's beta and R² change substantially depending on whether the benchmark is the broad market or the sector ETF. Choosing the right benchmark is not a technical detail; it determines every downstream risk and performance judgment.

---

*Completed as part of the Investments & Portfolio Management course. Tools used: Microsoft Excel, Minitab.*
