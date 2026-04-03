---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-51-6
id: US-WNE-51-9
points: 1
status: done
story_id: US-WNE-51
tags: []
title: 'Test: verify memory zeroization after Rust WgDevice drop'
updated: '2026-04-03'
---

Write a Rust integration test that creates a WgDevice with a known key, drops it, and then inspects the memory region (via unsafe raw pointer snapshot taken before drop) to confirm the key bytes have been zeroed. Test both private key and PSK fields. This validates the zeroize crate integration works end-to-end.