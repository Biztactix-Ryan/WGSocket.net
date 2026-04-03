---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-12-7
points: 2
status: done
story_id: US-WNE-12
tags: []
title: Implement Span-based receive buffer marshalling
updated: '2026-03-26'
---

Create BufferMarshaller.Receive helper that accepts Span<byte> buffer, pins it with fixed statement, passes the pointer and capacity to NativeMethods.wg_recv. Return the number of bytes actually written. If native returns WG_ERR_BUFFER_TOO_SMALL, throw WgBufferTooSmallException with required size if available. Validate buffer is not empty.