---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-9
points: 2
status: todo
story_id: US-WNE-62
tags: []
title: Implement fuzz target for wg_device_new with arbitrary configs
updated: '2026-03-26'
---

Create a fuzz target that feeds arbitrary byte sequences as config strings to wg_device_new. Cover malformed JSON/TOML, invalid key lengths, null bytes, oversized strings, empty strings, and valid-but-unusual configurations. Assert no panics or segfaults -- only clean error codes returned.