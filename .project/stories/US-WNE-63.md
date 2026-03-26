---
acceptance_criteria:
- Test NetworkStream wraps Socket correctly
- Test Read delegates to Socket.Receive
- Test Write delegates to Socket.Send
- Test ReadAsync/WriteAsync delegate to async socket methods
- Test CanRead/CanWrite/CanSeek values
- Test Dispose optionally closes underlying socket
- Test Stream-based APIs (StreamReader/StreamWriter) work
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-63
points: 2
priority: should
status: backlog
tags:
- testing
- api-surface
title: NetworkStream tests
updated: '2026-03-26'
---

As a developer, I want unit tests for the WgNetworkStream wrapper so that I can verify it correctly delegates to the underlying WgSocket for read/write operations and is compatible with standard .NET Stream-based APIs like StreamReader and StreamWriter.