---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-5-6
points: 2
status: todo
story_id: US-WNE-5
tags: []
title: Implement Tunn instance creation from private key and peer config
updated: '2026-03-26'
---

Create a wrapper module (e.g. wg.rs) that takes a WireGuard private key (x25519) and peer public key + optional preshared key + endpoint and constructs a boringtun Tunn instance. Parse key formats (base64). Store the Tunn in a struct that also holds peer metadata (allowed IPs, endpoint). Return errors for invalid keys or config.