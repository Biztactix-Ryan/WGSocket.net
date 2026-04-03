---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-47-8
points: 3
status: done
story_id: US-WNE-47
tags: []
title: Implement BenchmarkDotNet benchmark harness for tunnel throughput
updated: '2026-04-03'
---

Create a BenchmarkDotNet project (WgSocket.Benchmarks) with a benchmark class that measures TCP throughput through a WgTunnelPair. Include benchmarks for: single-stream throughput with configurable buffer sizes (4KB, 64KB, 256KB), latency measurement (small packet roundtrip time), and baseline direct-socket comparison (same test without tunnel). Configure BenchmarkDotNet for CI-friendly output (JSON/CSV export).