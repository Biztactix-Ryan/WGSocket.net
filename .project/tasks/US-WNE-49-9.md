---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-49-7
- US-WNE-49-8
id: US-WNE-49-9
points: 3
status: todo
story_id: US-WNE-49
tags: []
title: 'Test: WgSocket connects to wireguard-go peer'
updated: '2026-03-26'
---

Write integration test (with [Skip] if wireguard-go unavailable) that starts a wireguard-go instance as a server, creates a WgSocket device configured as its peer, verifies handshake completes between the two implementations, and sends/receives data through the cross-implementation tunnel.