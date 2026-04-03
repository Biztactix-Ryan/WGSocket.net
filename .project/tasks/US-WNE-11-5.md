---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-11-5
points: 2
status: done
story_id: US-WNE-11
tags: []
title: Define WgException hierarchy
updated: '2026-03-26'
---

Create WgException base class extending Exception with an int ErrorCode property and standard constructors (message, message+inner). Create subclasses: WgInvalidHandleException (invalid or closed handle), WgConnectionRefusedException (peer unreachable), WgBufferTooSmallException (buffer length insufficient), WgKeyException (invalid key material), WgTimeoutException (operation timed out). Each subclass sets a default message template and error code range.