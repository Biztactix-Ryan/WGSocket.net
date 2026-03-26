---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-46-8
points: 1
status: todo
story_id: US-WNE-46
tags: []
title: Scaffold SafeHandle test infrastructure with mock release callbacks
updated: '2026-03-26'
---

Create SafeHandleTests.cs with test infrastructure that tracks native handle release calls. Implement a mock native release function (via INativeMethodsProxy) that records call count and handle values. This enables verifying that ReleaseHandle is called exactly once per handle, in the correct order, without requiring the actual Rust library.