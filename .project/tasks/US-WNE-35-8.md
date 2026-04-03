---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-35-6
- US-WNE-35-7
id: US-WNE-35-8
points: 2
status: done
story_id: US-WNE-35
tags: []
title: Test handle map safety and secure memory cleanup
updated: '2026-03-26'
---

Test creating multiple devices and verifying unique handles are assigned. Test that get() with a valid handle returns the device. Test that get() with an invalid handle returns an error code. Test that get() with a previously-removed handle returns an error. Test ref-counting: create device, open socket (incrementing ref count), try to destroy device -- verify it stays alive until socket is closed. Test zeroize: after device cleanup, read the memory region and verify key bytes are zeroed (may require unsafe test code or zeroize's built-in assertions). Test concurrent handle operations from multiple threads.