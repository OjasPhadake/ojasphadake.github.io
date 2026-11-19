---
layout: page
title: Equity Alpha Research
description: About 100 equity alphas with ablations, decorrelation and meta-blending
importance: 4
category: quant
---

**Systematic equity alpha research.** _(Code is not public.)_

**What I did.** I built about **100 equity alpha signals** across several idea families, including stochastic-oscillator signals, volume-stability filters, intraday signals, and a meta-blend of the strongest ideas.

**How I judged them.** I treated every signal as a hypothesis to falsify, not as a PnL curve to admire:

- **Ablations:** removing one component at a time to see what actually carries the signal.
- **Robustness:** stability across sub-periods and parameter perturbations.
- **Decorrelation analysis:** a new alpha only counts if it adds information beyond the existing ones.
- **Risk-adjusted selection:** information ratio, plus IR/√turnover so that high-turnover signals don't win on paper only.

The result was a shortlist of decorrelated candidates and a short write-up covering what worked, what failed and why.
