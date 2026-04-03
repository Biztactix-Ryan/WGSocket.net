---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-39-6
id: US-WNE-39-9
points: 2
status: done
story_id: US-WNE-39
tags: []
title: 'Test: Rapid small message stress test'
updated: '2026-03-28'
---

Write integration test that sends 1000+ small messages (64-256 bytes each) rapidly in both directions. Verify all messages are received in order with correct content. Tests the tunnel under high message-rate load to catch race conditions or buffer overflow issues.