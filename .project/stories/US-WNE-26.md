---
acceptance_criteria:
- NetworkStream(Socket socket) constructor wraps a WgSocket.Socket
- Inherits from System.IO.Stream
- Read/Write/ReadAsync/WriteAsync delegate to underlying socket Send/Receive methods
- CanRead/CanWrite/CanSeek report correctly (CanSeek is false)
- Disposing NetworkStream optionally disposes underlying socket (ownsSocket parameter)
- Compatible with StreamReader/StreamWriter and ASP.NET Core and HttpClient
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-26
points: 3
priority: must
status: done
tags:
- api
- stream
- mvp
title: WgSocket.NetworkStream wrapper
updated: '2026-03-27'
---

As a library consumer, I want a NetworkStream that wraps WgSocket.Socket so that I can use Stream-based APIs like ASP.NET Core Kestrel, HttpClient, StreamReader, and StreamWriter over WireGuard tunnels.