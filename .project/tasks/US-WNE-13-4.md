---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-13-5
id: US-WNE-13-4
points: 1
status: done
story_id: US-WNE-13
tags: []
title: 'Test: Custom resolver falls back to default when custom probing fails'
updated: '2026-03-26'
---

Verify that when the custom DllImportResolver does not find the library in runtimes/{rid}/native/, it returns IntPtr.Zero to allow the default .NET resolution to proceed. Test that the default resolver can still find the library if it is on the system PATH or in the app directory.