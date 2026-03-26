---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-38-9
points: 1
status: todo
story_id: US-WNE-38
tags: []
title: Implement TCP echo client helper for integration tests
updated: '2026-03-26'
---

Create a TcpEchoClient helper that connects to a tunnel IP, sends a byte[] payload, and reads back the echoed response. Supports configurable send/receive buffer sizes. Provides both sync and async API variants. Returns the received bytes for comparison. Includes timeout protection on all operations.