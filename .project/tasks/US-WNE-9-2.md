---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-9-5
- US-WNE-9-6
- US-WNE-9-7
id: US-WNE-9-2
points: 1
status: todo
story_id: US-WNE-9
tags: []
title: 'Test: Marshalling attributes are correct for all P/Invoke parameters'
updated: '2026-03-26'
---

Write reflection-based tests that verify marshalling attributes on each P/Invoke parameter: string parameters have UTF-8 marshalling, pointer parameters use nint or unsafe byte*, buffer parameters pair a pointer with a length parameter. Verify return types match expected C ABI types.