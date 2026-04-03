---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-59-5
- US-WNE-59-6
id: US-WNE-59-7
points: 2
status: done
story_id: US-WNE-59
tags: []
title: 'Test: full lifecycle log capture confirms no key material leakage'
updated: '2026-04-03'
---

Write integration tests on both Rust and C# sides that enable all log levels (Trace/Debug/Info/Warn/Error/Critical), perform a complete device lifecycle (create, connect, send, receive, dispose), capture all log output to a buffer, and assert via pattern matching that no raw key material (base64 or hex encoded private keys, PSKs) appears anywhere in the captured output.