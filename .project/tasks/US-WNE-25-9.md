---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-25-9
points: 3
status: todo
story_id: US-WNE-25
tags: []
title: Create boringtun test harness with paired tunnels
updated: '2026-03-26'
---

Build a test harness module that creates two boringtun Tunn instances configured as peers of each other (matching key pairs, AllowedIPs). Provide helper functions: create_tunnel_pair() returning (Tunn, Tunn), feed_packet(src, dst) that passes output of src into dst (simulating network), and drive_handshake(a, b) that completes a full Noise IK handshake between the pair. This harness is needed by all crypto and packet composition tests.