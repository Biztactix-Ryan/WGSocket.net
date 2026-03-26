---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-13-6
id: US-WNE-13-2
points: 1
status: todo
story_id: US-WNE-13
tags: []
title: 'Test: DllNotFoundException contains helpful diagnostic message'
updated: '2026-03-26'
---

Test that when the native library is not found, the thrown DllNotFoundException message includes: the current RuntimeIdentifier, the expected file path with platform-correct extension (.so/.dylib/.dll), and a suggestion to install WgSocket.Native.{rid}. Test on the current platform and verify the extension matches.