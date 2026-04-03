---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-15-6
points: 2
status: done
story_id: US-WNE-15
tags: []
title: Implement outbound packet path (smoltcp -> boringtun -> UDP)
updated: '2026-03-26'
---

In tunnel.rs, implement the outbound data path. When smoltcp's virtual device transmit() produces an IP packet: pass it to boringtun Tunn::encapsulate() to encrypt into a WireGuard transport message. Queue the encrypted packet for sending on the real UDP socket. Handle the case where encapsulate() returns multiple packets (e.g. handshake + data). Buffer outbound packets when the UDP socket would block.