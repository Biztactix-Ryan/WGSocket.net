---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-8-7
points: 2
status: todo
story_id: US-WNE-8
tags: []
title: Implement TCP and UDP socket creation and lifecycle
updated: '2026-03-26'
---

Implement functions to create TCP and UDP sockets on the smoltcp Interface. For TCP: support bind, listen, connect, accept operations mapped to smoltcp socket API. For UDP: support bind and send_to/recv_from. Manage socket handles in a collection on the device. Configure socket buffer sizes with sensible defaults (64KB TCP rx/tx, 16KB UDP) and accept user overrides. Track socket state for cleanup.