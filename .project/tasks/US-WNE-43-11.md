---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-43-7
id: US-WNE-43-11
points: 1
status: todo
story_id: US-WNE-43
tags: []
title: 'Test: Handshake timeout with unreachable peer'
updated: '2026-03-26'
---

Write integration test creating a WgDevice configured with a peer endpoint that is unreachable (e.g. localhost port with nothing listening, or a black-hole IP). Verify the handshake attempt times out within the expected window. Verify the device reports appropriate error state. Verify the device does not crash or leak resources.