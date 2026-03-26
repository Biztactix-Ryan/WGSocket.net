---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-11
points: 1
status: todo
story_id: US-WNE-62
tags: []
title: Implement fuzz target for wg_connect with arbitrary addresses
updated: '2026-03-26'
---

Create a fuzz target for wg_connect that exercises arbitrary IP address strings, port numbers (0, 65535, overflow values), malformed address formats, null pointers, and extremely long strings. Verify all inputs produce clean error codes or success.