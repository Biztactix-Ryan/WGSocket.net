---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-51-7
points: 2
status: todo
story_id: US-WNE-51
tags: []
title: Implement secure key handling on C# side with fixed/pinned buffers
updated: '2026-03-26'
---

Replace any plain string or byte[] key parameters with fixed/pinned buffer patterns. Use ReadOnlySpan<byte> for key passing at the P/Invoke boundary. Add explicit zeroing (Array.Clear or Span.Clear) in Dispose paths. Ensure no managed string copies of key material exist. Use CriticalFinalizerObject or SafeHandle to guarantee cleanup.