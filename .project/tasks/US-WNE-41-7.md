---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-41-6
id: US-WNE-41-7
points: 1
status: todo
story_id: US-WNE-41
tags: []
title: 'Test: Traffic to allowed IP succeeds with /32 restriction'
updated: '2026-03-26'
---

Write integration test configuring a peer with AllowedIPs = 10.0.0.1/32. Verify that TCP connection and data transfer to 10.0.0.1 succeeds. Verify the handshake completes and data roundtrips correctly through the restricted configuration.