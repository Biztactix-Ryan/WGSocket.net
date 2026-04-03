---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-40-7
id: US-WNE-40-9
points: 2
status: done
story_id: US-WNE-40
tags: []
title: 'Test: Star topology with hub device'
updated: '2026-04-03'
---

Write integration test creating a star topology with one hub device and 3 spoke devices. Hub can communicate with all spokes. Verify spokes cannot communicate with each other directly (no peer config). Test that AllowedIPs correctly routes traffic through the hub only to intended destinations.