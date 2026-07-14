# Investments & Portfolio Management — Project 2

A quantitative equity analysis project covering portfolio optimisation, asset pricing model estimation, and index model regression across two retail stocks (TGT and WMT) and the SPDR S&P Retail ETF (XRT).

## Overview

The project is divided into three sections, each building on the previous:

1. **Descriptive analysis and optimal portfolio construction** using historical returns
2. **CAPM and Fama-French three-factor model estimation** with regression via Minitab
3. **Index model analysis** using the retail sector ETF (XRT) as the benchmark

---

## Section 1 — Descriptive Analysis & Portfolio Optimisation

Monthly return data for Target (TGT) and Walmart (WMT) was used to compute individual stock statistics and construct the optimal risky portfolio by maximising the Sharpe ratio.

**Stock-level statistics:**

| Metric | TGT | WMT |
|---|---|---|
| Average Monthly Return | 1.26% | 1.22% |
| Standard Deviation | 8.99% | 5.33% |
| Sharpe Ratio | 0.1187 | 0.1915 |
| Correlation (TGT–WMT) | 0.432 | 0.432 |

**Optimal risky portfolio (historical returns, r_f = 0.2%/month):**

| Weight TGT | Weight WMT | Portfolio Return | Portfolio Risk | Sharpe Ratio |
|---|---|---|---|---|
| 21.88% | 78.12% | 1.23% | 5.32% | 0.1937 |

WMT dominates the optimal portfolio due to its superior Sharpe ratio and lower volatility. The moderate correlation (0.432) provides meaningful diversification benefit.

---

## Section 2 — CAPM & Fama-French Three-Factor Model

Excess returns were computed using the Fama-French risk-free rate. Regressions were run in Minitab against the market excess return (Mkt–RF) for CAPM, and additionally against SMB and HML factors for the three-factor model.

### CAPM Results

| Stock | Alpha | Beta | Expected Return | Risk |
|---|---|---|---|---|
| TGT | 0.00168 (p=0.823, insig.) | 1.012 ✓ | 0.707% | 8.99% |
| WMT | 0.00683 (p=0.162, insig.) | 0.428 ✓ | 0.414% | 5.33% |

- **TGT beta ≈ 1** — moves near one-for-one with the market; consistent with retail sector cyclicality
- **WMT beta = 0.428** — defensive stock; demand for essentials is recession-resistant
- **Neither alpha is statistically significant** — both stocks are fully explained by market risk; no evidence of abnormal returns

### Fama-French Three-Factor Results

| Stock | Alpha | Market β | SMB β | HML β | Expected Return |
|---|---|---|---|---|---|
| TGT | 0.00306 (insig.) | 1.003 | 0.058 (insig.) | –0.049 (insig.) | 0.707% |
| WMT | 0.00481 (insig.) | 0.527 | 0.533 | –0.180 | 0.339% |

- TGT loads only on the market factor — large-cap, no meaningful size or value tilt
- WMT shows significant SMB loading (0.533), suggesting exposure to small-cap risk premia despite being a mega-cap — likely a structural factor in the retail sector
- Negative HML betas on both stocks suggest a mild growth orientation

### Optimal Risky Portfolio Comparison

| Method | Weight TGT | Weight WMT | Sharpe Ratio |
|---|---|---|---|
| Historical Returns | 21.88% | 78.12% | **0.1937** |
| CAPM-based | 59.40% | 40.60% | 0.059 |
| Fama-French-based | 94.13% | 5.87% | 0.0566 |

The historical Sharpe ratio is highest but likely overfitted to the sample period. The CAPM portfolio is preferred among model-based approaches — it is theoretically grounded, more conservative, and offers a better Sharpe ratio than the Fama-French portfolio with lower risk.

---

## Section 3 — Index Model (XRT Retail ETF)

TGT's excess returns were regressed against the retail sector ETF (XRT) rather than the broad market, isolating industry-specific risk.

**XRT Index Model results for TGT:**

| Measure | Value |
|---|---|
| Alpha | 0.00669 |
| Beta | 0.6273 |
| Systematic Variance | 0.002612 |
| Idiosyncratic Variance | 0.005486 |
| Total Variance | 0.008081 |
| R² | 0.3232 |
| Information Ratio | 0.0905 |

**CAPM vs. Index Model comparison:**

| Model | Benchmark | Beta | R² |
|---|---|---|---|
| CAPM | Broad market (Mkt–RF) | 1.012 | 0.2856 |
| Index Model | Retail ETF (XRT) | 0.6273 | 0.3232 |

The lower beta under the index model reflects that TGT does not move one-for-one with the *entire* market, only with the retail sector. The higher R² under the index model confirms that industry-level movements explain more of TGT's return variation than the broad market does — the retail ETF is the more relevant benchmark for a sector-specific stock.

---

## Skills Demonstrated

| Area | Tools & Techniques |
|---|---|
| Portfolio Theory | Mean-variance optimisation, Sharpe ratio maximisation, correlation-based diversification |
| Asset Pricing | CAPM, Fama-French three-factor model, alpha/beta estimation |
| Regression Analysis | OLS regression in Minitab, statistical significance testing (p-values), R² interpretation |
| Risk Decomposition | Systematic vs. idiosyncratic variance, Information Ratio |
| Index Models | Sector ETF as benchmark, industry vs. market beta comparison |

---

## Key Takeaways

- A statistically significant beta does not guarantee a high R² — sensitivity and explanatory power are distinct concepts
- Historical Sharpe ratios overfit to sample periods; model-based expected returns are more reliable for forward-looking portfolio construction
- Industry-level benchmarks can explain more return variation than the broad market for sector-concentrated stocks

---

*Completed as part of the Investments & Portfolio Management course. Tools used: Microsoft Excel, Minitab.*
