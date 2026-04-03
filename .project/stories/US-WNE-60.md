---
acceptance_criteria:
- Test Socket constructor creates valid instance
- Test Connect/ConnectAsync method signatures match expected
- Test Bind/Listen/Accept/AcceptAsync signatures
- Test Send/SendAsync/Receive/ReceiveAsync signatures
- Test Close/Dispose releases resources
- Test property accessors (Connected and LocalEndPoint and RemoteEndPoint and Available)
- Test state validation (Send before Connect throws)
- Test Blocking property toggle
- Test CancellationToken support in async methods
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-60
points: 5
priority: must
status: done
tags:
- testing
- mvp
- api-surface
title: Socket API surface tests
updated: '2026-04-03'
---

As a developer, I want comprehensive unit tests for the WgSocket API surface so that I can verify the socket type provides a familiar System.Net.Sockets.Socket-compatible interface and that all method signatures, property accessors, state validation, and async patterns work as expected for drop-in replacement usage.