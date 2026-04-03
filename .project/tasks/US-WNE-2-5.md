---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-2-5
points: 1
status: done
story_id: US-WNE-2
tags: []
title: Define WgConfig and WgPeerConfig structs
updated: '2026-03-26'
---

Create the core config data model in src/config.rs. Define WgConfig with fields: private_key ([u8; 32]), listen_port (Option<u16>), address (Vec<IpNet>), dns (Vec<IpAddr>), peers (Vec<WgPeerConfig>). Define WgPeerConfig with fields: public_key ([u8; 32]), endpoint (Option<SocketAddr or String>), allowed_ips (Vec<IpNet>), preshared_key (Option<[u8; 32]>), persistent_keepalive (Option<u16>). Derive Clone on both structs. Use ipnet crate for CIDR types.