---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-27-8
id: US-WNE-27-9
points: 2
status: done
story_id: US-WNE-27
tags: []
title: Implement TCP socket lifecycle tests
updated: '2026-03-27'
---

Using the smoltcp harness, write tests that: open a TCP socket and bind/listen on a port, verify it enters the Listen state; connect a second TCP socket to the listening socket via loopback, verify both reach Established; send data from client to server and verify exact bytes received; send data from server to client (bidirectional); close the connection gracefully and verify both sockets reach Closed; verify socket resources are freed after close (handle can be reused).