---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-38-8
- US-WNE-38-9
id: US-WNE-38-13
points: 2
status: done
story_id: US-WNE-38
tags: []
title: 'Test: TCP echo via sync and async API paths'
updated: '2026-03-28'
---

Write integration tests that exercise the same echo roundtrip through both the synchronous API (blocking calls) and the asynchronous API (async/await). Verify both paths produce identical results. Ensure async path properly uses ValueTask/Task without blocking the thread pool.