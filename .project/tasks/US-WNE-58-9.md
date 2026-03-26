---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-58-7
id: US-WNE-58-9
points: 2
status: todo
story_id: US-WNE-58
tags: []
title: Add XML doc comments to WgDevice, WgConfig, and WgPeer types
updated: '2026-03-26'
---

Add comprehensive XML documentation to WgDevice, WgConfig, and WgPeer classes: summary for each type describing its role in the WireGuard setup flow, summary/param/returns/exception for all public methods (device creation, configuration loading, peer management), and summary for all public properties (PrivateKey, PublicKey, ListenPort, Address, AllowedIPs, Endpoint, etc.). Use see-cref cross-references between related types.