---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-44-8
id: US-WNE-44-10
points: 1
status: done
story_id: US-WNE-44
tags: []
title: 'Test: Clean disconnect via FIN handshake'
updated: '2026-03-29'
---

Write integration test where a client connects, transfers data, then gracefully disconnects. Verify the server side receives end-of-stream. Verify both sides can close their sockets cleanly. Verify the smoltcp TCP state machine transitions through FIN_WAIT correctly.