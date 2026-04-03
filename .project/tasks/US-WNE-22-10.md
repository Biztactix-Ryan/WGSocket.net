---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-22-9
id: US-WNE-22-10
points: 2
status: done
story_id: US-WNE-22
tags: []
title: Implement Socket.Connect and Socket.Bind
updated: '2026-03-27'
---

Connect(IPEndPoint remoteEP): validate state is Created or Bound, call NativeMethods.wg_connect with tunnel handle and endpoint, transition state to Connected, set RemoteEndPoint. Bind(IPEndPoint localEP): validate state is Created, call NativeMethods.wg_bind, transition state to Bound, set LocalEndPoint. Both throw SocketException on native failure with appropriate SocketError codes matching System.Net.Sockets behavior.