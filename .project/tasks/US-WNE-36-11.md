---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-36-7
- US-WNE-36-8
- US-WNE-36-9
- US-WNE-36-10
id: US-WNE-36-11
points: 2
status: done
story_id: US-WNE-36
tags: []
title: 'Test: Verify test harness creates functional paired tunnel'
updated: '2026-03-28'
---

Write integration tests verifying: keypair generation produces valid 32-byte keys, WgTunnelPair creates two devices that complete handshake within 5 seconds, tunnel IPs are correctly assigned, disposal cleans up both devices and releases UDP ports, and the harness works without any network access beyond localhost.