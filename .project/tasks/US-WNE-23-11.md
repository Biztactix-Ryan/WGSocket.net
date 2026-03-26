---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-23-10
id: US-WNE-23-11
points: 2
status: todo
story_id: US-WNE-23
tags: []
title: Implement config parsing happy-path tests
updated: '2026-03-26'
---

Write unit tests in config.rs (or tests/config_tests.rs) covering: parse valid single-peer config and assert all fields match expected values; parse valid multi-peer config and assert peer count and per-peer fields; parse config with all optional fields (PresharedKey, PersistentKeepalive, DNS) and assert each is present and correct; parse config with comments and extra whitespace and assert clean parse; test config builder round-trip (parse then serialize, compare output). Each test should use fixtures from the helper module.