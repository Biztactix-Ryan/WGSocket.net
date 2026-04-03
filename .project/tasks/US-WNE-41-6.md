---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-41-6
points: 2
status: done
story_id: US-WNE-41
tags: []
title: Implement AllowedIPs test configuration helpers
updated: '2026-03-28'
---

Create helpers that configure WgDevice peers with specific AllowedIPs CIDR ranges for testing. Support configuring /32, /24, /16, and /0 ranges. Provide methods to create a device pair where one side has restricted AllowedIPs and the other has open AllowedIPs. Include helpers to attempt connections to IPs both inside and outside the allowed range.