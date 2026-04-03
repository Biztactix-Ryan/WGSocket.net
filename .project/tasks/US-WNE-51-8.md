---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-51-6
id: US-WNE-51-8
points: 1
status: done
story_id: US-WNE-51
tags: []
title: Redact key material from Debug/Display trait implementations
updated: '2026-04-03'
---

Implement custom Debug and Display traits for all Rust types containing key material. Output must show '[REDACTED]' instead of actual key bytes. Audit all fmt::Debug derives on key-holding structs and replace with manual impls. Same treatment for any C# ToString overrides on key wrapper types.