---
acceptance_criteria:
- Measure single-stream TCP throughput (bytes/sec) through tunnel
- Measure latency (roundtrip time for small packets)
- Compare against baseline (direct socket with no tunnel) to quantify overhead
- Test with different buffer sizes (4KB and 64KB and 256KB)
- Test sustained transfer (100MB+) for stability
- Results logged to console/file for CI tracking
- BenchmarkDotNet or similar for reproducible results
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-47
points: 5
priority: should
status: done
tags:
- testing
- integration
- performance
- benchmarks
title: Performance and throughput benchmarks
updated: '2026-04-03'
---

As a developer, I want reproducible performance benchmarks measuring throughput and latency through the WireGuard tunnel so that I can quantify overhead, detect regressions, and establish performance baselines for CI tracking.