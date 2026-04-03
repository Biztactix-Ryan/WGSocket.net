---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-6-5
- US-WNE-6-6
id: US-WNE-6-7
points: 2
status: done
story_id: US-WNE-6
tags: []
title: Tests for config builder
updated: '2026-03-26'
---

Write unit tests for the builder: test building a minimal valid config (private key + one peer with public key and allowed IP) succeeds; test fluent chaining syntax compiles and works; test build() with missing private key returns error; test build() with no peers returns error; test building a multi-peer config; test that raw byte slice keys work (not just base64); test building a config and comparing it to one parsed from an equivalent wg.conf string (round-trip equivalence); test PeerBuilder.done() returns control to ConfigBuilder correctly.