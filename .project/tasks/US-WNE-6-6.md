---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-6-5
id: US-WNE-6-6
points: 2
status: done
story_id: US-WNE-6
tags: []
title: Implement PeerBuilder and build() finalization
updated: '2026-03-26'
---

Create PeerBuilder for constructing peer configs: .peer() on ConfigBuilder returns a PeerBuilder, PeerBuilder has .public_key(key: &[u8; 32]), .endpoint(ep: &str), .allowed_ip(cidr: &str), .preshared_key(key: &[u8; 32]), .persistent_keepalive(secs: u16), and .done() to return back to ConfigBuilder. Implement .build() -> Result<WgConfig, Vec<ConfigError>> on ConfigBuilder that assembles the config and calls validate(). Accept raw byte slices for all key inputs.