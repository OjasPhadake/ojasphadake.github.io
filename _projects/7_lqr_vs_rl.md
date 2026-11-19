---
layout: page
title: LQR vs Reinforcement Learning
description: PPO rediscovers the optimal linear feedback law without knowing the dynamics
img: assets/img/projects/lqr-vs-rl.png
importance: 2
category: control
github: https://github.com/OjasPhadake/LQRvsRL
---

**[Code on GitHub](https://github.com/OjasPhadake/LQRvsRL)** · Python · Gymnasium · Stable-Baselines3

**Question.** LQR and PPO are solving the same Bellman equation; the only difference is what each knows. LQR is given the system matrices and solves the Riccati equation exactly. PPO learns from interaction alone. How close does the model-free learner get?

**Setup.** A discrete-time double integrator (marginally stable, so it needs active feedback) in a custom Gymnasium environment, with an infinite-horizon quadratic cost. LQR comes from the discrete algebraic Riccati equation; PPO trains for 100k steps.

**Results.** PPO lands within **0.26% of the LQR cost**, and its actions correlate with LQR's at **r = 0.987**. It effectively rediscovers the linear law u ≈ −Kx without ever seeing A or B.

<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">{% include figure.liquid loading="eager" path="assets/img/projects/lqr-vs-rl.png" title="LQR vs PPO trajectories" class="img-fluid rounded z-depth-1" %}</div>
  <div class="col-sm-6 mt-3 mt-md-0">{% include figure.liquid loading="eager" path="assets/img/projects/lqr-vs-rl-curve.png" title="PPO learning curve" class="img-fluid rounded z-depth-1" %}</div>
</div>
<div class="caption">Left: LQR and PPO trajectories overlaid. Right: the PPO learning curve against the LQR reward (dashed).</div>
