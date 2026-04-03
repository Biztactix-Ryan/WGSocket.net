---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-10-7
id: US-WNE-10-2
points: 1
status: done
story_id: US-WNE-10
tags: []
title: 'Test: WgSocketHandle lifecycle and platform-conditional IsInvalid'
updated: '2026-03-26'
---

Test that WgSocketHandle reports IsInvalid=true for -1 on Unix and INVALID_HANDLE_VALUE on Windows. Verify ReleaseHandle calls wg_socket_close. Test that valid fd values return IsInvalid=false. Test double-dispose is safe.