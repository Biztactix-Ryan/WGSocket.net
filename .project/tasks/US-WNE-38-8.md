---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-38-8
points: 2
status: todo
story_id: US-WNE-38
tags: []
title: Implement TCP echo server helper for integration tests
updated: '2026-03-26'
---

Create a TcpEchoServer helper that listens on a WgDevice's tunnel IP and echoes received bytes back to the client. Supports both sync (blocking) and async operation modes. Handles multiple sequential connections. Logs bytes received/sent for test assertions. Runs as a background task with cancellation token support.