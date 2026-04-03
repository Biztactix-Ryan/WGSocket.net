---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-22-9
points: 2
status: done
story_id: US-WNE-22
tags: []
title: Implement Socket class scaffold and constructor
updated: '2026-03-27'
---

Create WgSocket.Socket class in the WgSocket namespace. Internal constructor accepts a native tunnel handle from WgDevice.CreateSocket(). Store the handle, initialize internal state (SocketState enum: Created, Bound, Listening, Connected, Closed). Implement IDisposable. Add internal reference back to parent WgDevice for ref-count management. Match System.Net.Sockets.Socket constructor overload signatures where applicable.