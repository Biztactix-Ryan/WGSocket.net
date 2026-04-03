---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-33-9
points: 1
status: done
story_id: US-WNE-33
tags: []
title: Scaffold WgConfigTests and WgPeerTests test classes
updated: '2026-03-27'
---

Create WgConfigTests.cs and WgPeerTests.cs in the WgSocket.Tests project. Set up xUnit test class structure with shared test fixtures for valid WireGuard keys (base64-encoded 32-byte keys), valid endpoints, and valid CIDR ranges. Include helper methods for generating test WgConfig and WgPeer instances with known-good defaults.