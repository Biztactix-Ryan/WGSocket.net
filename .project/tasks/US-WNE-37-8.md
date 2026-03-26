---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-37-7
id: US-WNE-37-8
points: 2
status: todo
story_id: US-WNE-37
tags: []
title: Implement NativeMethods declaration and string marshalling tests
updated: '2026-03-26'
---

Write tests that verify NativeMethods declarations have correct DllImport attributes, calling conventions, and CharSet settings. Test that managed strings are marshalled to UTF-8 with null terminators when passed to native code via the mock proxy. Verify round-trip: managed string -> UTF-8 bytes -> back to managed string preserves content including Unicode characters.