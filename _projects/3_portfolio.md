---
layout: page
title: Quantitative Portfolio Construction
description: Mean-variance, HRP and shrinkage portfolios, plus a leakage-free LightGBM alpha model
img: assets/img/projects/portfolio-frontier.png
importance: 3
category: quant
github: https://github.com/sparshgupta02/D6701_Projects
---

**[Code on GitHub](https://github.com/sparshgupta02/D6701_Projects)** · Team project (5 members), course DA6701 · Python · SciPy · LightGBM

A set of portfolio-construction studies on Indian equities. The ones I worked on:

**Mean-variance optimization.** I picked 10 diversified holdings from a 30-stock universe with a least-correlation selection algorithm, then solved for the Global Minimum Variance and Max-Sharpe portfolios with constrained optimization (SLSQP). The Max-Sharpe portfolio reached a **Sharpe ratio of 2.26 against 1.62** for GMV, benchmarked against 10,000 Monte Carlo portfolios.

**ML alpha forecasting.** A lagged, leakage-free pipeline (OHLCV, macro, fundamentals, FinBERT sentiment) for 6 large-cap stocks. It selects the top 25 features per ticker with Ridge + RFE and trains LightGBM under 5-fold walk-forward cross-validation. The train/out-of-sample RMSE ratio stayed between 1.26× and 1.40× to guard against overfitting.

**Robust covariance.** The sample covariance matrix was ill-conditioned (κ = 30.5). Ledoit-Wolf shrinkage cut the condition number by **53%**. I compared this against Hierarchical Risk Parity, which avoids matrix inversion altogether, over a 48-month backtest, measuring turnover and stress-testing on the 2008 banking crisis.

<div class="row">
  <div class="col-sm mt-3 mt-md-0">{% include figure.liquid loading="eager" path="assets/img/projects/portfolio-frontier.png" title="Efficient frontier" class="img-fluid rounded z-depth-1" %}</div>
  <div class="col-sm mt-3 mt-md-0">{% include figure.liquid loading="eager" path="assets/img/projects/portfolio-turnover.png" title="Turnover" class="img-fluid rounded z-depth-1" %}</div>
</div>
<div class="caption">Left: Monte Carlo efficient frontier with the GMV and Max-Sharpe portfolios. Right: monthly turnover of mean-variance vs HRP portfolios. HRP stays far more stable.</div>
