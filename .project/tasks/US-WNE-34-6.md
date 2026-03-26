---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-34-6
points: 2
status: todo
story_id: US-WNE-34
tags: []
title: Implement socket and resource release tests
updated: '2026-03-26'
---

Write tests that: create a device, open multiple sockets (TCP and UDP), then free the device and verify all socket handles become invalid; verify that after device free, attempting to send or receive on any previously-opened socket returns an appropriate error; verify the I/O thread (if any) terminates within a reasonable timeout after device free by checking thread join or a shutdown flag.