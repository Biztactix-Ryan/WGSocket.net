---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-15-8
points: 3
status: todo
story_id: US-WNE-15
tags: []
title: Implement handshake packet routing and timer integration
updated: '2026-03-26'
---

Ensure handshake packets (message types 1-4) are routed correctly: they go between boringtun and the UDP socket only, never to smoltcp. Integrate boringtun timer handling into the composition loop: call update_timers() at the correct interval, process resulting actions (send keepalive, initiate rekey, etc.). Track tunnel state transitions and log them. Handle the case where tunnel is not yet established (queue smoltcp packets until handshake completes).