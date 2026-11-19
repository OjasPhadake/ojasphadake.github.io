---
layout: page
title: Project SMAC
description: ADMM motion planning with control barrier functions for safe navigation
importance: 4
category: control
github: https://github.com/OjasPhadake/ProjectSMAC
---

**[Code on GitHub](https://github.com/OjasPhadake/ProjectSMAC)** · State Space Modelling and Control, Mathematics Club, IIT Madras · I was Project Strategist

**Goal.** Safe, smooth navigation around non-convex obstacles, with safety enforced by the controller rather than hoped for.

**What we built.**

- **Layered control with ADMM:** a trajectory planner and a trajectory generator coordinated through the Alternating Direction Method of Multipliers. A new cost function gives low-jerk, smooth paths around non-convex obstacles.
- **Control barrier functions:** exponential and higher-order CBFs added to the layered controller enforce forward invariance of the safe set. In simulation, higher-order CBFs reduced collision probability by **31%**.
- **Extensions:** an MPC-CBF hybrid, pursuit-evasion and dynamic-obstacle scenarios, plus Hidden Markov Models for regime detection in financial time series.

{% include figure.liquid loading="eager" path="assets/img/projects/smac.png" title="CBF safety analysis" class="img-fluid rounded z-depth-1" %}

<div class="caption">Baseline study: a first-order CBF safety filter on particle dynamics, with collisions dropping from 48% to 38% of runs. The 31% figure above comes from the separate higher-order CBF experiments.</div>
