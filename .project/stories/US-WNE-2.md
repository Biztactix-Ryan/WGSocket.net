---
acceptance_criteria:
- WgConfig struct with private_key listen_port and address fields
- WgPeerConfig struct with public_key endpoint allowed_ips preshared_key and persistent_keepalive
  fields
- All key fields use fixed-size byte arrays ([u8; 32]) not Strings
- Config structs derive Clone and Debug with key fields redacted in Debug output
created: '2026-03-26'
epic_id: EPIC-WNE-2
id: US-WNE-2
points: 2
priority: must
status: done
tags:
- rust
- config
- mvp
title: WireGuard config data model
updated: '2026-03-26'
---

As a developer, I want Rust structs representing WireGuard configuration so that config can be passed around type-safely.