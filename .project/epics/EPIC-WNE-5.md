---
created: '2026-03-26'
id: EPIC-WNE-5
points: null
priority: must
status: draft
tags:
- csharp
- api
- mvp
target_date: null
title: C# Public API (Socket-Compatible)
updated: '2026-03-26'
---

Implement the consumer-facing C# API that mirrors System.Net.Sockets.Socket. The end goal is a single-file import experience: `using WgSocket;` and swap `new Socket(...)` for `new WgSocket.Socket(...)`. Includes WgDevice (tunnel lifecycle with IDisposable), WgSocket.Socket (Connect, Bind, Listen, Accept, Send, Receive + async variants), WgPeer (peer config model), WgConfig (configuration model), and WgSocket.NetworkStream (Stream wrapper for ASP.NET Core / HttpClient compatibility).