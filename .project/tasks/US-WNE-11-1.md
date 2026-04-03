---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-11-5
id: US-WNE-11-1
points: 1
status: done
story_id: US-WNE-11
tags: []
title: 'Test: WgException hierarchy structure and ErrorCode property'
updated: '2026-03-26'
---

Verify WgException extends Exception and has an int ErrorCode property. Test each subclass (WgInvalidHandleException, WgConnectionRefusedException, WgBufferTooSmallException, WgKeyException, WgTimeoutException) extends WgException. Verify default messages are set. Verify serialization round-trips preserve ErrorCode. Test constructor overloads (message, message+inner).