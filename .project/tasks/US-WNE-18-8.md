---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-18-6
- US-WNE-18-7
id: US-WNE-18-8
points: 2
status: done
story_id: US-WNE-18
tags: []
title: 'Test send/recv: full transfer, partial transfer, would-block, null buffer,
  closed socket'
updated: '2026-03-26'
---

Write integration tests: (1) send N bytes and recv same N bytes through a connected socket pair, (2) send more than buffer capacity returns partial byte count, (3) recv on empty buffer returns WG_ERR_WOULD_BLOCK, (4) send/recv with null buffer returns error without crash, (5) send/recv with zero length returns error, (6) send/recv on closed socket returns WG_ERR_CLOSED, (7) send/recv with invalid handle returns WG_ERR_INVALID_HANDLE.