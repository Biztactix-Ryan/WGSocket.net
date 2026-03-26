---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-36-8
points: 2
status: todo
story_id: US-WNE-36
tags: []
title: Implement WgTunnelPair test fixture for paired WgDevice creation
updated: '2026-03-26'
---

Create a WgTunnelPair class that creates two WgDevice instances configured as mutual peers over localhost UDP. Assigns sequential tunnel IPs (e.g. 10.0.0.1 and 10.0.0.2), picks random available UDP ports, configures each device with the other's public key in AllowedIPs, and exposes DeviceA, DeviceB, TunnelIpA, TunnelIpB properties. Implements IAsyncDisposable for cleanup.