# Cross-Sectional Momentum and Moving Average Strategies in Crypto Markets
## Abstract

This project implements and evaluates systematic trading strategies in cryptocurrency markets using daily Binance data. 
We test (1) a **cross-sectional momentum strategy** and (2)  **moving average crossover** strategy. Strategies are optimized in-sample and evaluated out-of-sample with transaction costs. Performance is assessed using Sharpe ratio, alpha, beta, drawdowns, and turnover metrics.

---
# Data
Daily spot prices for a basket of cryptocurrencies

- Source: Binance API
- Sample split: Training: pre-2022, Test: 2022 onward

Returns are computed from daily closes. Duplicate timestamps are removed and data integrity checks are applied.

---
# Methodology
1. Cross-Sectional Momentum
- Signal: Rolling average return over varying lookback horizons
- Portfolio: Demeaned, normalized cross-sectional ranks (long/short, dollar-neutral)
- Optimization: Grid search over lookback window
- Transaction costs: 20 bps per turnover

2. Moving Average Crossover
- Signal: Short MA − Long MA
- Portfolio: Demeaned, normalized cross-sectional ranks (long/short, dollar-neutral)
- Optimization: Grid search over (short, long) window pairs
- Transaction costs: 20bps per turnover

---
# Evaluation Framework

Performance is measured using:
- Annualized Sharpe ratio
- Yearly Sharpe stability
- Alpha and beta (regression vs BTC)
- Correlation to BTC and equal-weight crypto basket
- Maximum drawdown and duration
- Average holding period
- Net performance after turnover-adjusted costs

---
# Results

- Momentum delivers consistent risk-adjusted performance and statistically significant alpha. Moving average strategy is more regime-sensitive and exhibits higher variability.
- Transaction costs materially reduce high-turnover profitability.
- A volatility-weighted combination improves stability and drawdown characteristics.
