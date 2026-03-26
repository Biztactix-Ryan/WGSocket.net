---
acceptance_criteria:
- Test TCP socket open/bind/listen/accept on smoltcp interface
- Test TCP connect to listening socket (loopback)
- Test data send/receive through smoltcp TCP
- Test UDP socket send/receive
- Test socket buffer sizing
- Test multiple concurrent sockets on same interface
- Test socket close and resource cleanup
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-27
points: 3
priority: must
status: backlog
tags:
- rust
- testing
- smoltcp
- networking
- unit-test
title: smoltcp interface tests
updated: '2026-03-26'
---

As a developer, I want tests for the smoltcp virtual network interface so that I can verify TCP/UDP socket operations, buffer management, and concurrent socket handling work correctly on the userspace network stack.