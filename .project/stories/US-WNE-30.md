---
acceptance_criteria:
- Test full outbound path (app data to smoltcp to boringtun to encrypted packet)
- Test full inbound path (encrypted packet to boringtun to smoltcp to app data)
- Test bidirectional data flow through two paired tunnels
- Test handshake completes between two tunnel instances
- Test data flows after successful handshake
- Test large payload (>MTU) fragmentation and reassembly
- Test concurrent sends from multiple sockets
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-30
points: 5
priority: must
status: backlog
tags:
- rust
- testing
- integration
- tunnel
title: Tunnel composition integration tests
updated: '2026-03-26'
---

As a developer, I want integration tests that exercise the full tunnel pipeline (smoltcp to boringtun and back) so that I can verify end-to-end encrypted data flow including handshake, fragmentation, and concurrent access.