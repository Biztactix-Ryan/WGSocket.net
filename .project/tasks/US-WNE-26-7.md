---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-26-7
points: 1
status: todo
story_id: US-WNE-26
tags: []
title: Implement NetworkStream class inheriting System.IO.Stream
updated: '2026-03-26'
---

Create WgSocket.NetworkStream class inheriting System.IO.Stream. Constructor NetworkStream(Socket socket, bool ownsSocket = false) stores reference to WgSocket.Socket and ownership flag. Override CanRead => true, CanWrite => true, CanSeek => false. Override Length/Position to throw NotSupportedException. Override Seek/SetLength to throw NotSupportedException. Implement Flush() as no-op (socket sends are not buffered).