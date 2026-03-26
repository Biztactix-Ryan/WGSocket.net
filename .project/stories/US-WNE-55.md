---
acceptance_criteria:
- Console app in samples/EchoServer/ with its own .csproj referencing WgSocket
- Demonstrates WgDevice setup and configuration from wg.conf
- Uses Socket.Listen and Accept to handle incoming connections
- Implements a full echo loop that reads data and writes it back
- Includes a wg.conf with test configuration and key pair for local testing
- Runs against the ChatClient sample or any other WgSocket peer
- Includes README.md with usage instructions and expected output
- Shows the single-file import experience prominently with 'using WgSocket' as the
  only namespace change
created: '2026-03-26'
epic_id: EPIC-WNE-11
id: US-WNE-55
points: 3
priority: should
status: backlog
tags:
- samples
- docs
- mvp
title: EchoServer sample application
updated: '2026-03-26'
---

As a developer evaluating WgSocket.net, I want a working EchoServer sample so that I can see the single-file import experience and understand how to set up a TCP listener over a WireGuard tunnel in minutes.