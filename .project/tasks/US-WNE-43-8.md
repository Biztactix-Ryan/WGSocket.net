---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-43-7
id: US-WNE-43-8
points: 1
status: done
story_id: US-WNE-43
tags: []
title: 'Test: Initial Noise_IKpsk2 handshake completes and data flows'
updated: '2026-03-28'
---

Write integration test creating a WgTunnelPair and verifying: handshake completes within 5 seconds, both peers report a valid last-handshake timestamp, and data can flow in both directions immediately after handshake. Assert the handshake used the Noise_IKpsk2 protocol (via session metadata if exposed).