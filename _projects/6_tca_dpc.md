---
layout: page
title: TCA-DPC
description: Adapting diffusion controllers to new safety constraints at test time (arXiv 2026)
importance: 1
category: control
github: https://github.com/ojasph/tca-dpc
---

**[Paper](https://arxiv.org/abs/2611.19380) · [Code](https://github.com/ojasph/tca-dpc)** · Aalto University, Cyber-physical Systems Group · PyTorch

**Problem.** A diffusion model trained on demonstrations can act as a predictive controller by sampling candidate state-input sequences. But if a new obstacle appears at deployment, sequences the model still finds likely may be unsafe. Retraining every time the constraints change is impractical.

**Method.** We treat the pretrained diffusion model as a prior and **exponentially tilt** it with a constraint-violation penalty. Tilting suppresses unsafe sequences but keeps the relative probabilities of the safe ones. We sample this tilted distribution with the **Metropolis-adjusted Langevin algorithm in the sampler's Gaussian noise space**, back-propagating through the full denoising chain. The tilt strength is set online by feedback on the fraction of sampled sequences that fail verification. The method needs no retraining, no projection and no explicit obstacle geometry.

**My role.** I ran all the simulations and the numerical study, benchmarking against the projection-based DPCC method on the D3IL robot-manipulator _Avoiding_ task.

**Results.** Without any constraint tightening, the method reaches **82.7% goal-and-constraint success**, against 61.3% for the untilted baseline and 71.3% for DPCC. Constraint-violating steps per episode fall from 3.17 to **0.73**.

{% include figure.liquid loading="eager" path="assets/img/projects/tca-dpc.png" title="TCA-DPC results" class="img-fluid rounded z-depth-1" %}

<div class="caption">(a) Closed-loop paths: the pretrained prior (grey) vs TCA-DPC (blue) around a new forbidden region. (b) The tilt strength rises after the first verification failure and relaxes once failures become rare. (c) Success vs constraint tightening.</div>
