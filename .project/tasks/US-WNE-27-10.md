---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-27-8
id: US-WNE-27-10
points: 2
status: done
story_id: US-WNE-27
tags: []
title: Implement UDP and concurrent socket tests
updated: '2026-03-27'
---

Using the smoltcp harness, write tests that: send and receive a UDP datagram through the interface; verify UDP with various payload sizes including empty; open multiple TCP sockets on the same interface and verify they can operate concurrently without interference; test socket buffer sizing by configuring small buffers and verifying backpressure behavior (send blocks or returns WouldBlock when buffer full).