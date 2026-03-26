---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-62-8
- US-WNE-62-9
- US-WNE-62-10
- US-WNE-62-11
- US-WNE-62-12
id: US-WNE-62-14
points: 2
status: todo
story_id: US-WNE-62
tags: []
title: 'Test: verify fuzz corpus seeds produce no panics or UB'
updated: '2026-03-26'
---

Create a deterministic test that runs each fuzz target's seed corpus through the harness under Miri (where possible) or AddressSanitizer. This serves as a regression gate: if any seed corpus entry causes a panic, segfault, or sanitizer finding, CI fails. Validates the fuzz infrastructure itself works correctly.