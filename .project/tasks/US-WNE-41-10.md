---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-41-6
id: US-WNE-41-10
points: 2
status: done
story_id: US-WNE-41
tags: []
title: 'Test: Various CIDR ranges (/32, /24, /16, /0)'
updated: '2026-03-28'
---

Write parameterized integration test (xUnit [Theory]) testing AllowedIPs with /32, /24, /16, and /0 CIDR masks. For each mask, verify that IPs within range succeed and IPs outside range are dropped. /0 should allow all traffic (wildcard).