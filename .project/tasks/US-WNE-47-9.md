---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-47-9
points: 2
status: todo
story_id: US-WNE-47
tags: []
title: Implement sustained transfer stability benchmark
updated: '2026-03-26'
---

Create a benchmark that transfers 100MB+ of data through the tunnel in a sustained stream. Monitor for memory leaks (GC pressure), throughput degradation over time, and errors. Log throughput samples at regular intervals to detect performance cliffs. This is not a BenchmarkDotNet microbenchmark but a longer-running stability test.