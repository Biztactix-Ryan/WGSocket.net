---
acceptance_criteria:
- Test each error code maps to correct exception type
- Test exception message includes native error detail
- Test WgException.ErrorCode property
- Test throwing and catching specific exception types
- Test error codes not in enum produce generic WgException
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-54
points: 2
priority: must
status: done
tags:
- testing
- mvp
- error-handling
title: Exception mapping tests
updated: '2026-03-27'
---

As a developer, I want unit tests for the exception mapping layer so that I can verify every native error code is translated to the correct managed exception type with meaningful messages and that the exception hierarchy is well-structured.