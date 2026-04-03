---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-25-9
id: US-WNE-25-10
points: 2
status: done
story_id: US-WNE-25
tags: []
title: Implement WireGuard message format and handshake tests
updated: '2026-03-27'
---

Using the tunnel pair harness, write tests that: verify handshake initiation message has correct type byte (1) and length (148 bytes); verify handshake response message has correct type byte (2) and length (92 bytes); verify encrypt produces transport data messages (type 4) with valid header (receiver index + counter); verify keepalive is a transport message with zero-length payload. Assert exact byte positions per the WireGuard protocol spec.