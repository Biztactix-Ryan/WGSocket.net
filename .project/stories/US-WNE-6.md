---
acceptance_criteria:
- Builder pattern with fluent API (ConfigBuilder::new().private_key(...).peer(...).build())
- Accepts raw byte slices for keys (not just base64 strings)
- Validates on build() call reusing the config validation logic
- Can construct config equivalent to any valid wg.conf file
created: '2026-03-26'
epic_id: EPIC-WNE-2
id: US-WNE-6
points: 2
priority: must
status: backlog
tags:
- rust
- config
- builder
- mvp
title: Programmatic config builder
updated: '2026-03-26'
---

As a developer, I want a builder API for constructing configs in code so that the C FFI can pass config without file I/O.