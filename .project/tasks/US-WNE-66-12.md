---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-66-8
- US-WNE-66-9
id: US-WNE-66-12
points: 2
status: done
story_id: US-WNE-66
tags: []
title: 'Test: rapid create/dispose cycles under thread contention'
updated: '2026-04-03'
---

Write a stress test (both Rust and C#) that spawns multiple threads each rapidly creating and disposing devices and sockets in tight loops. Run for at least 10 seconds. Assert no crashes, no use-after-free (validate with AddressSanitizer on Rust side), and no unhandled exceptions on C# side. Verify ref-counting holds under contention.