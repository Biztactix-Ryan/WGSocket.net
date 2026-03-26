---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-15-6
- US-WNE-15-7
- US-WNE-15-8
id: US-WNE-15-9
points: 3
status: todo
story_id: US-WNE-15
tags: []
title: Test full outbound and inbound packet flow through composition engine
updated: '2026-03-26'
---

Create two tunnel.rs composition engines configured as peers. Drive a handshake between them by exchanging packets via in-memory channel (no real UDP). Send a TCP SYN through engine A's smoltcp, verify it arrives encrypted, decrypt through engine B, and verify smoltcp on B receives the SYN. Complete a full TCP handshake and data exchange through both engines. Verify handshake packets never reach smoltcp. Test timer-driven keepalive generation. Test UDP socket data flow through the composition.