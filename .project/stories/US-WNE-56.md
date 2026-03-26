---
acceptance_criteria:
- Console app in samples/ChatClient/ with its own .csproj referencing WgSocket
- Demonstrates WgDevice setup and configuration from wg.conf
- Uses Socket.Connect to establish outbound connection to a peer
- Interactive send/receive loop with console input and output
- Bidirectional messaging over WireGuard tunnel
- Uses async API (ReadAsync/WriteAsync via NetworkStream) for non-blocking I/O
- Includes wg.conf with test configuration and key pair for local testing
- Includes README.md with usage instructions and expected output
created: '2026-03-26'
epic_id: EPIC-WNE-11
id: US-WNE-56
points: 3
priority: should
status: backlog
tags:
- samples
- docs
- mvp
title: ChatClient sample application
updated: '2026-03-26'
---

As a developer evaluating WgSocket.net, I want a working ChatClient sample so that I can see how to build interactive bidirectional communication over a WireGuard tunnel using the async API.