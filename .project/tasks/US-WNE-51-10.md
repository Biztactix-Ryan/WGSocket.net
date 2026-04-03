---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-51-7
id: US-WNE-51-10
points: 1
status: done
story_id: US-WNE-51
tags: []
title: 'Test: verify C# key buffer zeroing after Dispose'
updated: '2026-04-03'
---

Write a C# test that creates a WgSocket with known key material, disposes it, and verifies the pinned buffer contents are zeroed. Use GCHandle or fixed statement to pin and inspect memory. Test under both normal Dispose and finalizer paths.