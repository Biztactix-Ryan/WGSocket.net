---
acceptance_criteria:
- Connected property reflects current connection state
- LocalEndPoint and RemoteEndPoint properties return correct IPEndPoints
- Available property reports bytes ready to read
- SocketType and ProtocolType properties expose socket configuration
- Blocking property toggles synchronous mode behavior
- State transitions validated with clear exceptions (e.g. cannot Send before Connect)
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-29
points: 2
priority: must
status: done
tags:
- api
- socket
- state
title: Socket properties & state management
updated: '2026-03-27'
---

As a library consumer, I want Socket properties and state management that match System.Net.Sockets.Socket so that my existing code patterns (checking Connected, reading endpoints, validating state) work without changes.