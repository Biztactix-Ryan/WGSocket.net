---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-44-8
id: US-WNE-44-12
points: 2
status: done
story_id: US-WNE-44
tags: []
title: 'Test: Reconnect after disconnect and socket reuse'
updated: '2026-03-29'
---

Write integration test verifying: after a clean disconnect, a new connection can be established to the same tunnel endpoint; after closing a socket, the same port can be reused for a new listener; a blocked receive times out with the configured timeout rather than hanging indefinitely.