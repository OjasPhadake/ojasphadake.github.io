---
layout: page
title: Drift-Aware Trading ML Platform
description: Low-latency prediction service with drift detection and automated retraining
importance: 2
category: quant
github: https://github.com/OjasPhadake/Stock-Price-Prediction-Project
---

**[Code on GitHub](https://github.com/OjasPhadake/Stock-Price-Prediction-Project)** · Python · DVC · MLflow · FastAPI · Docker · Prometheus · Grafana

**Problem.** A model that predicts well at deployment decays as market regimes shift. A production system has to notice the decay and react without a human watching it.

**What I built.** An end-to-end platform for next-day equity direction prediction:

- **Data and features:** a version-controlled 5-stage DVC pipeline turns raw yfinance OHLCV data into 22 quantitative signals.
- **Training:** experiments are tracked in MLflow, and models are promoted through a model registry.
- **Serving:** a 4-service Dockerized REST platform (FastAPI) serves real-time predictions at **under 80 ms p95 latency**.
- **Monitoring:** Kolmogorov–Smirnov drift detection on feature distributions (threshold 0.1), Prometheus/Grafana alerts when the error rate exceeds 5%, and a scheduler that retrains unattended once drift is detected.

**Why it matters for trading.** It's the operational side of a live signal: reproducible features, fast inference, and automatic detection of regime change.
