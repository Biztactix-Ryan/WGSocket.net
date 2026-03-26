---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-41-6
id: US-WNE-41-9
points: 2
status: todo
story_id: US-WNE-41
tags: []
title: 'Test: Packets from wrong source IP are dropped'
updated: '2026-03-26'
---

Write integration test verifying that if a device receives an inner packet claiming to be from an IP not in the peer's AllowedIPs, it is dropped. Configure two devices where the AllowedIPs do not match the actual tunnel IP assignment and verify communication fails.