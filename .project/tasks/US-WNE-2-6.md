---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-2-5
id: US-WNE-2-6
points: 1
status: done
story_id: US-WNE-2
tags: []
title: Implement custom Debug for key redaction
updated: '2026-03-26'
---

Implement fmt::Debug manually for WgConfig and WgPeerConfig so that key fields (private_key, public_key, preshared_key) are printed as '[REDACTED]' instead of raw bytes. This prevents accidental key leakage in logs. Other fields should display normally.