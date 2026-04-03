---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-3-6
- US-WNE-3-7
- US-WNE-3-8
- US-WNE-3-9
id: US-WNE-3-10
points: 2
status: done
story_id: US-WNE-3
tags: []
title: Tests for wg.conf parser
updated: '2026-03-26'
---

Write unit tests for the parser: test parsing a minimal valid config (one interface, one peer); test parsing a config with multiple peers; test that comments and blank lines are ignored; test that missing [Interface] section returns an error; test error messages include line numbers for malformed lines; test parsing of comma-separated AllowedIPs and Address values; test a full realistic wg.conf file (use an inline string constant matching real WireGuard output format).