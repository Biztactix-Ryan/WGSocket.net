---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-40-7
id: US-WNE-40-8
points: 3
status: todo
story_id: US-WNE-40
tags: []
title: 'Test: Three-peer mesh communication'
updated: '2026-03-26'
---

Write integration test creating three WgDevice instances in a full mesh. Verify Device A can send/receive with Device B, Device A can send/receive with Device C, and Device B can send/receive with Device C. Each peer pair uses independent handshakes. Use unique payloads per pair to verify correct routing.