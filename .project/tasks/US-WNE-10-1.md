---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-10-6
id: US-WNE-10-1
points: 1
status: todo
story_id: US-WNE-10
tags: []
title: 'Test: WgDeviceHandle lifecycle and IsInvalid'
updated: '2026-03-26'
---

Test that WgDeviceHandle reports IsInvalid=true for IntPtr.Zero. Test that a valid handle returns IsInvalid=false. Verify that calling Dispose sets IsClosed=true. Mock or stub wg_device_free to verify ReleaseHandle calls it exactly once. Test double-dispose does not throw.