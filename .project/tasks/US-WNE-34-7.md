---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-34-6
id: US-WNE-34-7
points: 3
status: todo
story_id: US-WNE-34
tags: []
title: Implement memory leak and key-zeroization tests
updated: '2026-03-26'
---

Write tests that: run a create/use/free cycle in a loop (100+ iterations) and verify handle map size does not grow (assert map length returns to baseline after each free); use a custom allocator or valgrind-compatible test attribute to detect memory leaks after a full create-send-receive-free cycle; after device free, verify that key material (private key bytes) has been zeroed in memory -- this may require a test-only accessor or inspecting the Zeroize trait implementation. Include a #[cfg(test)] accessor if needed for key memory inspection.