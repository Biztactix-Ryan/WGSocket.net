---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-36-9
points: 2
status: done
story_id: US-WNE-36
tags: []
title: Implement handshake wait and health check in test harness
updated: '2026-03-28'
---

Add WaitForHandshakeAsync(TimeSpan timeout) method to WgTunnelPair that polls both devices until a successful handshake is confirmed or timeout expires. Include a IsHealthy property that checks both devices are running and have completed at least one handshake. Throw descriptive exceptions on timeout with debug info (last handshake time, error counters).