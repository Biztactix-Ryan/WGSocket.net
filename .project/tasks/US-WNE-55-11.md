---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-55-10
id: US-WNE-55-11
points: 1
status: todo
story_id: US-WNE-55
tags: []
title: Create test wg.conf and sample README
updated: '2026-03-26'
---

Create samples/EchoServer/wg.conf with a pre-generated test key pair, tunnel address (e.g., 10.0.0.1/24), and listen port. Create samples/EchoServer/README.md documenting: prerequisites, how to generate keys, how to run the echo server, how to test with ChatClient or netcat over WgSocket, and expected output. Include the 'using WgSocket;' single-import highlight.