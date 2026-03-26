---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-59-6
points: 1
status: todo
story_id: US-WNE-59
tags: []
title: Audit and redact all C# log statements touching key material
updated: '2026-03-26'
---

Audit every ILogger call and structured logging field in the C# codebase. Ensure no log statement at any level includes key material. Use redacting wrappers or custom formatters for any key-adjacent structured log fields. Document the no-log rule in the code review checklist.