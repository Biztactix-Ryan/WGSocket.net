---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-9-5
- US-WNE-9-6
- US-WNE-9-7
id: US-WNE-9-1
points: 1
status: done
story_id: US-WNE-9
tags: []
title: 'Test: All LibraryImport declarations resolve correctly'
updated: '2026-03-26'
---

Write unit tests that verify every P/Invoke method in NativeMethods.cs has the [LibraryImport("wgsocket")] attribute via reflection. Assert that no method uses [DllImport]. Verify the partial class structure is present. Use a Roslyn analyzer test or reflection-based test to enumerate all extern methods.