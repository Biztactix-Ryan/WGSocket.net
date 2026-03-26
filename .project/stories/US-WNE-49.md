---
acceptance_criteria:
- Test WgSocket connecting to wireguard-go peer if available in CI
- Test wireguard-go connecting to WgSocket listener
- Verify handshake interop between implementations
- Verify data transfer between implementations
- Skip gracefully if wireguard-go not available
- Document how to set up the external peer for local testing
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-49
points: 5
priority: should
status: backlog
tags:
- testing
- integration
- interop
- wireguard-go
title: External WireGuard peer interop
updated: '2026-03-26'
---

As a developer, I want to verify that WgSocket can interoperate with external WireGuard implementations (wireguard-go) so that I can confirm protocol compatibility and real-world usability beyond the library's own tunnel stack.