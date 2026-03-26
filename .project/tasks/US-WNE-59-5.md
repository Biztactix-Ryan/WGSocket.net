---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-59-5
points: 2
status: todo
story_id: US-WNE-59
tags: []
title: Audit and redact all Rust log statements touching key material
updated: '2026-03-26'
---

Audit every tracing/log macro call in the Rust codebase. Ensure no log statement at any level (trace through error) includes private key, PSK, or session key values. Replace any key references with '[REDACTED]' or use the redacted Display impl. Add #[deny] lint or wrapper types that prevent accidental logging of secrets.