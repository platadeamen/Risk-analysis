# Portfolio Risk & Return Analysis

A quantitative analysis of risk and return across five companies, using Python to calculate volatility, Value at Risk (VaR), and cross-asset correlation — with the goal of identifying a diversified, risk-aware portfolio allocation.

## Overview

This project analyzes historical price data for five companies — **Dior, LVMH, L'Oréal, Ralph Lauren, and Hermes** (final selection may vary — update to match your chosen tickers) — to answer a practical investment question: *given their risk and return profiles, how should capital be allocated across them?*

The analysis covers:
- Daily and annualized return
- Annualized volatility (standard deviation of returns)
- Historical Value at Risk (VaR) at a 95% confidence level
- Correlation matrix between assets, used to evaluate diversification benefit

## Tools & Methodology

- **Data source:** Yahoo Finance, via the `yfinance` Python library
- **Environment:** Google Colab (Jupyter Notebook)
- **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`
- **VaR method:** Historical simulation (5th percentile of the daily return distribution)
- **Volatility scaling:** Daily standard deviation annualized using the square-root-of-time rule (× √252 trading days)

## Key Findings

- L'Oréal showed the most favorable risk profile in the sample, with the lowest VaR (-2.33%) among the analyzed companies.
- Hermès was the most volatile stock (37.42% annualized) and also delivered the highest annual return (36.15%), reflecting a higher risk-higher reward profile. This volatility was largely driven by geopolitical tensions in the Middle East, further compounded by weaker demand in China during Q1 2026.
- LVMH and Ralph Lauren showed high correlation (0.96) — moving almost in sync, which limits their combined diversification value in a portfolio.
- Hermès and L'Oréal showed low correlation (0.23), making them a more effective pairing for risk reduction, since a decline in one is not closely mirrored by the other.

## Suggested Allocation ($10,000 example)

| Asset | Allocation | Rationale |
|---|---|---|
| L'Oréal | $3,500 | Lowest VaR in the sample; anchors the conservative side of the portfolio |
| Hermès | $3,500 | Strong annual return; paired with L'Oréal due to low correlation (0.23) |
| Dior | $1,000 | Low correlation with the core pair; solid VaR (-2.90%) |
| Reserved | $2,000 | Held for future allocation into additional, higher-return opportunities |

## How to Run This Notebook

1. Open [Google Colab](https://colab.research.google.com)
2. Upload `portfolio_risk_analysis.ipynb`
3. Run all cells sequentially (Runtime → Run all)
4. Optionally edit the ticker list in the "Settings" cell to analyze different companies

## Repository Contents

- `portfolio_risk_analysis.ipynb` — full analysis notebook
- `images/` — exported charts (price trends, volatility comparison, VaR, correlation heatmap)
- `README.md` — this file

## Author

Aleksandr — prepared as part of independent preparation for undergraduate economics/finance studies.

## Limitations

Historical VaR assumes future returns will resemble the past distribution and does not capture tail risk beyond the confidence threshold — it does not estimate how large a loss could be in the worst 5% of cases (a limitation partially addressed by methods like Conditional VaR / Expected Shortfall). This analysis is for educational purposes and is not investment advice.
