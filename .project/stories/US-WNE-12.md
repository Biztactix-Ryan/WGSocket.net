---
acceptance_criteria:
- Send operations accept ReadOnlySpan<byte>
- Receive operations write to Span<byte>
- Pin managed buffers during P/Invoke calls using GCHandle or fixed
- Config strings marshalled as UTF-8 null-terminated
- Key material accepted as ReadOnlySpan<byte> (32 bytes) and never allocated as managed
  string
created: '2026-03-26'
epic_id: EPIC-WNE-4
id: US-WNE-12
points: 3
priority: must
status: done
tags:
- interop
- marshalling
- mvp
title: Buffer marshalling utilities
updated: '2026-03-26'
---

As a library developer, I want Span-based buffer marshalling utilities so that send/receive operations avoid unnecessary copies and key material is never allocated as managed strings.