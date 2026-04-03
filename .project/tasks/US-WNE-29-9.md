---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-29-7
- US-WNE-29-8
id: US-WNE-29-9
points: 2
status: done
story_id: US-WNE-29
tags: []
title: Test Socket properties and state transitions
updated: '2026-03-27'
---

Write xUnit tests covering: Connected is false initially and true after Connect, LocalEndPoint set after Bind, RemoteEndPoint set after Connect, Available returns correct value, SocketType and ProtocolType return expected values, Blocking property toggles, state transition validation (Send before Connect throws InvalidOperationException, Listen before Bind throws, Accept before Listen throws, Bind after Connect throws), properties after Close return defaults or throw appropriately.