---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-38-8
- US-WNE-38-9
id: US-WNE-38-10
points: 1
status: todo
story_id: US-WNE-38
tags: []
title: 'Test: TCP echo roundtrip with small payloads (1 byte, 100 bytes)'
updated: '2026-03-26'
---

Write integration test using WgTunnelPair that sends 1-byte and 100-byte payloads through the tunnel via TCP echo and verifies exact byte-for-byte match on return. Test with known patterns (all zeros, all ones, sequential bytes, random bytes).