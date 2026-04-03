---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-16-6
- US-WNE-16-7
- US-WNE-16-8
- US-WNE-16-9
id: US-WNE-16-10
points: 2
status: done
story_id: US-WNE-16
tags: []
title: 'Test connection lifecycle: connect, listen, accept, close, invalid handles'
updated: '2026-03-26'
---

Write integration tests: (1) wg_listen returns positive fd, (2) wg_connect to listening address returns positive fd, (3) wg_accept on listener returns new fd, (4) wg_close on each fd returns WG_OK, (5) wg_close on already-closed fd returns error, (6) all functions return WG_ERR_INVALID_HANDLE for bogus handle, (7) wg_connect with invalid address returns error with last-error detail.