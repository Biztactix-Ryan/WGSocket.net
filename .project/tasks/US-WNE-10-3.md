---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-10-6
- US-WNE-10-7
id: US-WNE-10-3
points: 1
status: done
story_id: US-WNE-10
tags: []
title: 'Test: ReleaseHandle calls correct native free function'
updated: '2026-03-26'
---

Using a test double or mock native library, verify that WgDeviceHandle.ReleaseHandle invokes wg_device_free with the correct handle value, and WgSocketHandle.ReleaseHandle invokes wg_socket_close with the correct fd. Verify the return value of ReleaseHandle reflects the native call success/failure.