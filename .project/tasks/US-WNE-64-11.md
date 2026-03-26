---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-64-9
id: US-WNE-64-11
points: 2
status: todo
story_id: US-WNE-64
tags: []
title: Implement CreateSocket and GetStats tests
updated: '2026-03-26'
---

Write tests verifying CreateSocket returns a valid WgSocket instance that is connected to the device's tunnel. Test that the returned socket's properties reflect the device state. Test GetStats returns a statistics object with expected fields (bytes sent, bytes received, last handshake time, etc.). Test CreateSocket after device disposal throws ObjectDisposedException. Test GetStats after disposal throws ObjectDisposedException.