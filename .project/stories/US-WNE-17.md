---
acceptance_criteria:
- WgConfig class with PrivateKey (byte[]) and ListenPort and Address and Peers collection
- WgPeer class with PublicKey and Endpoint and AllowedIPs and PresharedKey and PersistentKeepalive
- Validation on construction rejects invalid keys/ports/addresses
- ToString() redacts key material to prevent accidental logging
- Builder or object initializer pattern for ergonomic construction
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-17
points: 2
priority: must
status: backlog
tags:
- api
- models
- mvp
title: WgConfig & WgPeer configuration models
updated: '2026-03-26'
---

As a library consumer, I want strongly-typed configuration models (WgConfig and WgPeer) so that I can define WireGuard tunnel parameters with compile-time safety and validation.