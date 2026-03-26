---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-15-7
points: 3
status: todo
story_id: US-WNE-15
tags: []
title: Implement inbound packet path (UDP -> boringtun -> smoltcp)
updated: '2026-03-26'
---

In tunnel.rs, implement the inbound data path. When data arrives on the real UDP socket: pass it to boringtun Tunn::decapsulate(). If the result is a decrypted IP packet (WriteToTunnelV4/V6), feed it to smoltcp's virtual device receive queue. If the result is WriteToNetwork (handshake response), send that directly on the UDP socket without touching smoltcp. Handle chained results (decapsulate can return multiple actions). Drop malformed packets gracefully.