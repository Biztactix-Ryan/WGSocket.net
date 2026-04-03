---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-41-6
id: US-WNE-41-8
points: 2
status: done
story_id: US-WNE-41
tags: []
title: 'Test: Traffic to disallowed IP is silently dropped'
updated: '2026-03-28'
---

Write integration test configuring a peer with AllowedIPs = 10.0.0.1/32. Attempt to send traffic to 10.0.0.2 (outside the allowed range). Verify the connection fails or times out without crashing. Verify no data leaks to the wrong destination. Test with connection timeout to avoid hanging.