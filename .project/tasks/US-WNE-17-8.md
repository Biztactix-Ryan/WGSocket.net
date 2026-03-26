---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-17-6
- US-WNE-17-7
id: US-WNE-17-8
points: 1
status: todo
story_id: US-WNE-17
tags: []
title: Test WgPeer and WgConfig models
updated: '2026-03-26'
---

Write xUnit tests covering: valid construction of WgPeer and WgConfig, validation failures (wrong key length, invalid port, null address), ToString() redaction of key material, builder pattern usage, immutability of Peers collection, round-trip serialization if applicable. Cover edge cases: empty AllowedIPs, null optional fields, boundary port values (0, 65535).