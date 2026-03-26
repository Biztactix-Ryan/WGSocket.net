---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-3-8
points: 1
status: todo
story_id: US-WNE-3
tags: []
title: Implement Peer section parser
updated: '2026-03-26'
---

Parse [Peer] section tokens into WgPeerConfig structs. Map PublicKey to base64-decoded [u8; 32], Endpoint to string (validated later), AllowedIPs to Vec<IpNet> (comma-separated), PresharedKey to Option<[u8; 32]>, PersistentKeepalive to Option<u16>. Support multiple [Peer] sections by collecting into Vec<WgPeerConfig>. Return ConfigError::ParseError for unrecognized keys or malformed values.