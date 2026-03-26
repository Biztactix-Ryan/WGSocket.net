---
acceptance_criteria:
- WgException base class with ErrorCode property
- 'Specific subclasses: WgInvalidHandleException and WgConnectionRefusedException
  and WgBufferTooSmallException'
- Native error detail string from wg_last_error included in exception message
- Helper method that checks return code and throws if negative
created: '2026-03-26'
epic_id: EPIC-WNE-4
id: US-WNE-11
points: 2
priority: must
status: backlog
tags:
- interop
- exceptions
- mvp
title: Error code to exception mapping
updated: '2026-03-26'
---

As a library consumer, I want native WireGuard error codes mapped to a .NET exception hierarchy so that I can catch and handle specific failure modes idiomatically in C#.