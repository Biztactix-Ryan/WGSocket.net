---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-31-5
id: US-WNE-31-6
points: 1
status: done
story_id: US-WNE-31
tags: []
title: Test single-file import and namespace conflict scenarios
updated: '2026-03-27'
---

Write compilation-verification tests: a test file with only 'using WgSocket;' can access Socket, WgDevice, WgConfig, WgPeer, NetworkStream. A test file with both 'using WgSocket;' and 'using System.Net.Sockets;' can disambiguate via WgSocket.Socket vs System.Net.Sockets.Socket. Verify no ambiguous reference compiler errors in common usage patterns. Verify IntelliSense-relevant attributes (EditorBrowsable, DebuggerDisplay) are present.