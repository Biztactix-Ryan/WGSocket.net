---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-38-8
- US-WNE-38-9
id: US-WNE-38-12
points: 2
status: todo
story_id: US-WNE-38
tags: []
title: 'Test: TCP echo roundtrip with large payloads (1MB) testing fragmentation'
updated: '2026-03-26'
---

Write integration test sending 1MB payload through the tunnel. This exercises IP fragmentation/reassembly, TCP flow control, and sustained transfer through the boringtun encryption pipeline. Verify complete byte-for-byte integrity. Measure elapsed time for baseline.