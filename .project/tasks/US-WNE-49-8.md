---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-49-8
points: 2
status: todo
story_id: US-WNE-49
tags: []
title: Implement interop test configuration generator
updated: '2026-03-26'
---

Create a helper that generates matching WireGuard configurations for both WgSocket and wireguard-go. Generates a shared keypair set, assigns tunnel IPs, configures AllowedIPs, and outputs both a WgDeviceConfig object and a wireguard-go INI config file. Ensures both sides agree on all parameters for successful handshake.