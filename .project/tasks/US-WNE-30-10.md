---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-30-8
id: US-WNE-30-10
points: 3
status: todo
story_id: US-WNE-30
tags: []
title: Implement fragmentation and concurrency integration tests
updated: '2026-03-26'
---

Using the integrated tunnel harness, write tests that: send a payload larger than MTU (e.g. 4096 bytes over 1420-byte MTU) and verify complete reassembly on the receiving side; verify IP fragmentation headers are set correctly; open multiple sockets on one tunnel stack and send data concurrently from all of them, verify all data arrives correctly on the peer side; stress test with rapid sequential sends to verify no packet corruption.