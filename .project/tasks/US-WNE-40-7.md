---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-40-7
points: 3
status: done
story_id: US-WNE-40
tags: []
title: Implement WgMeshTopology test helper for multi-peer setup
updated: '2026-04-03'
---

Create a WgMeshTopology helper that configures N WgDevice instances in mesh or star topology. Each device gets a unique tunnel IP (10.0.0.1 through 10.0.0.N) and a unique localhost UDP port. Configures peer relationships based on a topology descriptor (full mesh, star, or custom adjacency). Implements IAsyncDisposable. Waits for all handshakes to complete before returning.