---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-44-8
points: 2
status: todo
story_id: US-WNE-44
tags: []
title: Implement connection lifecycle test helpers
updated: '2026-03-26'
---

Create helpers for testing connection edge cases: a method to attempt connection with configurable timeout, a method to dispose a device mid-transfer and capture the resulting exception, a helper to detect clean FIN vs abrupt RST disconnects, and a method to verify socket state after close (can it be reused). These helpers wrap the WgSocket API with assertion-friendly interfaces.