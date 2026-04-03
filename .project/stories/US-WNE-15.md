---
acceptance_criteria:
- 'Outbound path works: smoltcp IP packet -> boringtun encrypt -> UDP send'
- 'Inbound path works: UDP recv -> boringtun decrypt -> smoltcp process'
- Handshake packets are handled correctly and not fed to smoltcp
- Timer-driven events (keepalive and rekey) fire correctly
- The composition handles both TCP and UDP socket types
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-15
points: 8
priority: must
status: done
tags:
- rust
- tunnel
- composition
- mvp
title: Tunnel composition engine (tunnel.rs)
updated: '2026-03-26'
---

As a developer, I want the boringtun-smoltcp composition engine so that encrypted WireGuard packets flow correctly through the userspace TCP/IP stack.