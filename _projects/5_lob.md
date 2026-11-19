---
layout: page
title: Limit Order Book & Matching Engine
description: In progress. A C++ matching engine built for throughput and tail latency
importance: 5
category: quant
---

**Status: in progress** · C++

A miniature exchange core that supports limit and market orders, cancellations and partial fills under **price-time priority**, with trade events and deterministic replay.

**Plan:**

1. A `std::map`-based baseline for correctness.
2. Flat or hybrid price-level structures with intrusive order queues.
3. Memory pools and cache-aware layouts to remove allocations from the hot path.

**What gets measured:** throughput, median/p99/p99.9 latency, cycles per order, allocation counts and cache misses, on synthetic order flow scaling to millions of orders.

_The code will be linked here once the first benchmarked version is public._
