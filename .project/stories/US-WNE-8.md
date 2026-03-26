---
acceptance_criteria:
- Can create smoltcp Interface with a virtual device
- Can open TCP and UDP sockets on the interface
- Can bind/listen/connect/accept TCP sockets
- Socket buffers are correctly sized and configurable
- IP address and routing table configured from WireGuard AllowedIPs
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-8
points: 5
priority: must
status: backlog
tags:
- rust
- smoltcp
- networking
- mvp
title: smoltcp interface & socket management
updated: '2026-03-26'
---

As a developer, I want to create and manage smoltcp Interface and socket handles so that TCP/UDP connections can be established in userspace.