---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-38-8
- US-WNE-38-9
id: US-WNE-38-11
points: 2
status: todo
story_id: US-WNE-38
tags: []
title: 'Test: TCP echo roundtrip with medium payloads (1KB, 64KB)'
updated: '2026-03-26'
---

Write integration test sending 1KB and 64KB payloads through the tunnel. These sizes exercise smoltcp's TCP windowing and segmentation. Verify byte-for-byte match. Use random data to catch any bit-flipping or corruption in the crypto path.