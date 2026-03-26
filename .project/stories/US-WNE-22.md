---
acceptance_criteria:
- Connect(IPEndPoint) initiates TCP connection through the WireGuard tunnel
- Bind(IPEndPoint) binds to a tunnel address
- Listen(int backlog) starts listening for incoming connections
- Accept() returns new Socket for each accepted connection
- Send(ReadOnlySpan<byte>) sends data and returns bytes sent
- Receive(Span<byte>) receives data and returns bytes received
- Close() and Dispose() release native and managed resources
- Method signatures match System.Net.Sockets.Socket as closely as possible
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-22
points: 5
priority: must
status: backlog
tags:
- api
- socket
- sync
- mvp
title: WgSocket.Socket synchronous API
updated: '2026-03-26'
---

As a library consumer, I want a Socket class with synchronous methods that mirror System.Net.Sockets.Socket so that I can swap Socket types with a one-line change in existing synchronous code.