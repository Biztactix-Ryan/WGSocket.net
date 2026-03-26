---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-2-5
- US-WNE-2-6
- US-WNE-2-7
id: US-WNE-2-8
points: 1
status: todo
story_id: US-WNE-2
tags: []
title: Tests for config data model
updated: '2026-03-26'
---

Write unit tests for the config structs: test that WgConfig and WgPeerConfig can be constructed with valid field values; test Clone works correctly including deep copy of key arrays; test Debug output does NOT contain raw key bytes (assert the output contains '[REDACTED]'); test Debug output does show non-sensitive fields like listen_port and allowed_ips; test ConfigError Display messages are human-readable.