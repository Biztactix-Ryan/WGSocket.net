---
acceptance_criteria:
- Can create a boringtun Tunn instance from a private key and peer config
- Can encrypt plaintext IP packets into WireGuard transport messages
- Can decrypt incoming WireGuard packets to plaintext IP packets
- Handshake initiation and response work correctly
- Timer events (rekey and keepalive) are handled
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-5
points: 5
priority: must
status: done
tags:
- rust
- boringtun
- crypto
- mvp
title: boringtun tunnel integration
updated: '2026-03-26'
---

As a developer, I want to create and manage boringtun tunnel instances so that WireGuard handshakes and packet encryption/decryption work.