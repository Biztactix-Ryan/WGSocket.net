---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-43-7
id: US-WNE-43-10
points: 2
status: done
story_id: US-WNE-43
tags: []
title: 'Test: Handshake with PSK (pre-shared key)'
updated: '2026-03-28'
---

Write integration test creating a WgTunnelPair with a pre-shared key configured on both sides. Verify handshake completes successfully. Verify data transfer works. Then test with mismatched PSKs and verify handshake fails or data is unreadable.