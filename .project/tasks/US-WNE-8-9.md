---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-8-6
- US-WNE-8-7
- US-WNE-8-8
id: US-WNE-8-9
points: 2
status: done
story_id: US-WNE-8
tags: []
title: Test smoltcp socket operations with loopback virtual device
updated: '2026-03-26'
---

Create a smoltcp Interface with the virtual device in test configuration. Open a TCP socket, bind and listen on a port. Open a second TCP socket, connect to the listening socket. Drive the interface poll loop manually to complete the TCP handshake. Send data in both directions and verify delivery. Repeat for UDP bind/send_to/recv_from. Verify configurable buffer sizes take effect. Test AllowedIPs parsing with various CIDR notations.