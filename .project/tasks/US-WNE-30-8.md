---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-30-8
points: 3
status: done
story_id: US-WNE-30
tags: []
title: Create integrated tunnel test harness (smoltcp + boringtun)
updated: '2026-03-28'
---

Build an integration test harness that wires together two complete tunnel stacks: each stack has a smoltcp Interface connected to a boringtun Tunn, with the two Tunn instances peered. Provide helpers: create_tunnel_pair() returning two TunnelStack structs, pump_packets(a, b) that shuttles encrypted packets between the two stacks (simulating the network), and drive_until_connected(a, b) that completes handshake and verifies both sides have established sessions. This is the foundation for all tunnel integration tests.