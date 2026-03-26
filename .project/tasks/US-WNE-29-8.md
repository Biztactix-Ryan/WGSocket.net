---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-29-8
points: 2
status: todo
story_id: US-WNE-29
tags: []
title: Implement Socket type properties and state machine
updated: '2026-03-26'
---

Add SocketType property (returns SocketType.Stream for TCP). Add ProtocolType property (returns ProtocolType.Tcp). Add Blocking property (get/set) that toggles between blocking and non-blocking mode via NativeMethods.wg_set_blocking. Implement internal SocketState enum (Created, Bound, Listening, Connected, Closed) and state transition validation. ThrowIfDisposed() helper. InvalidOperationException with descriptive message for invalid transitions (e.g. 'Cannot Send on a socket that is not connected').