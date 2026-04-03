---
acceptance_criteria:
- Server device listens on tunnel IP and client device connects through tunnel
- Client sends byte[] through tunnel and server echoes it back
- Received data matches sent data exactly (byte-for-byte comparison)
- Works with small payloads (1 byte and 100 bytes)
- Works with medium payloads (1KB and 64KB)
- Works with large payloads (1MB -- tests fragmentation and reassembly)
- Test both sync and async API paths
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-38
points: 5
priority: must
status: done
tags:
- testing
- integration
- tcp
- mvp
title: TCP echo roundtrip test
updated: '2026-03-28'
---

As a developer, I want an end-to-end TCP echo test through a real WireGuard tunnel so that I can verify the full stack (C# API -> P/Invoke -> Rust FFI -> boringtun -> smoltcp -> UDP -> and back) works correctly with various payload sizes.