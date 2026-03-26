---
acceptance_criteria:
- Three or more WgDevice instances configured in a mesh or star topology
- Device A can communicate with Device B and Device C
- Devices B and C can communicate with each other when configured as peers
- Each peer relationship has independent handshakes
- Test message routing between non-directly-connected peers if applicable via AllowedIPs
- All peers can be created and torn down cleanly
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-40
points: 5
priority: should
status: backlog
tags:
- testing
- integration
- multi-peer
title: Multi-peer topology test
updated: '2026-03-26'
---

As a developer, I want to verify that three or more WgDevice instances can communicate in mesh or star topologies so that I can confirm the library supports real-world multi-peer deployments.