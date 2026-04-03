---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-30-8
id: US-WNE-30-9
points: 3
status: todo
story_id: US-WNE-30
tags: []
title: Implement end-to-end data path integration tests
updated: '2026-04-03'
---

Using the integrated tunnel harness, write tests that: send application data on stack A's smoltcp TCP socket, pump packets, and verify it arrives on stack B's smoltcp TCP socket (full outbound path); do the reverse direction (full inbound path); run bidirectional simultaneous data flow; verify handshake completes between two fresh tunnel instances before data can flow; verify data flows correctly after handshake completes.