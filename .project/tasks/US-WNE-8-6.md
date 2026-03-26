---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-8-6
points: 2
status: todo
story_id: US-WNE-8
tags: []
title: Implement smoltcp virtual device and Interface creation
updated: '2026-03-26'
---

Create a VirtualDevice struct implementing smoltcp's Device trait. The device acts as a packet pipe: transmit() queues IP packets for boringtun encryption, receive() dequeues decrypted IP packets from boringtun. Configure MTU (default 1420 for WireGuard). Create smoltcp Interface with the virtual device, setting hardware capabilities (medium = Ip, no checksums needed). Accept IP address and subnet configuration parameters.