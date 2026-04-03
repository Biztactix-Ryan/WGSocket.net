---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-11-5
id: US-WNE-11-6
points: 1
status: done
story_id: US-WNE-11
tags: []
title: Implement ThrowIfError helper and wg_last_error integration
updated: '2026-03-26'
---

Create a static NativeErrors.ThrowIfError(int returnCode) method that: returns immediately if returnCode >= 0; calls NativeMethods.wg_last_error() to get the native error string; maps the error code to the appropriate WgException subclass via a switch expression; includes both the native error string and the managed error code in the exception. Add an overload ThrowIfError(int returnCode, string context) for call-site context in the message.