---
layout: page
title: Data-Driven Optimal Control via Offline Policy Iteration
description: Model-free finite-horizon LQR for time-varying systems from one batch of data
img: assets/img/projects/offline-pi.png
importance: 3
category: control
github: https://github.com/OjasPhadake/Data-Driven-Optimal-Control-via-Offline-Policy-Iteration
---

**[Code on GitHub](https://github.com/OjasPhadake/Data-Driven-Optimal-Control-via-Offline-Policy-Iteration)** · MATLAB · Reproduction of Pang, Bian & Jiang (IEEE CDC 2018)

**Problem.** Finite-horizon LQR for a linear _time-varying_ system normally means solving a backward Riccati recursion, which needs the exact system matrices at every step. Can the optimal time-varying gains be learned from measured trajectories alone?

**Method.** Off-policy policy iteration. Each policy-evaluation step is solved as a least-squares regression on one batch of offline trajectory data, and that same batch is reused across every iteration. The system matrices are never identified. I built up to it in three stages (exact Riccati, model-based PI, then data-driven PI) and validated each against the exact solution.

**Results.** The learned value function converges to the exact Riccati solution within about 8 iterations. The learned controller cuts terminal-state error by **99.98%** and cost by **11.5×** relative to the uncontrolled system.

{% include figure.liquid loading="eager" path="assets/img/projects/offline-pi.png" title="Convergence across iterations" class="img-fluid rounded z-depth-1" %}

<div class="caption">Gap between the learned value function and the exact Riccati solution, by time step. Each colour is one policy-iteration step; the error falls by about an order of magnitude per iteration.</div>
