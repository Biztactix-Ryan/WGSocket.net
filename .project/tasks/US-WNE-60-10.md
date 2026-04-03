---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-60-10
points: 1
status: done
story_id: US-WNE-60
tags: []
title: Scaffold WgSocketTests with mock native backend
updated: '2026-04-03'
---

Create WgSocketTests.cs with test infrastructure for the Socket API surface. Set up a mock INativeMethodsProxy that simulates socket creation, connection, and data transfer at the P/Invoke boundary. Include helper methods for creating test socket instances in various states (unconnected, connected, listening, disposed). This mock layer enables testing all socket behavior without the Rust native library.