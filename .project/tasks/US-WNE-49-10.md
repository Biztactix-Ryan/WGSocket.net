---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-49-7
- US-WNE-49-8
id: US-WNE-49-10
points: 3
status: todo
story_id: US-WNE-49
tags: []
title: 'Test: wireguard-go connects to WgSocket listener'
updated: '2026-03-26'
---

Write integration test (with [Skip] if wireguard-go unavailable) that starts a WgSocket device as a listener, starts wireguard-go configured as its peer with WgSocket's endpoint, verifies handshake initiated by wireguard-go completes, and performs bidirectional data transfer. Verifies both directions of interop initiation.