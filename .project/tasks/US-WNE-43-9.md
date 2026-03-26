---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-43-7
id: US-WNE-43-9
points: 3
status: todo
story_id: US-WNE-43
tags: []
title: 'Test: Rekey occurs and data continues flowing'
updated: '2026-03-26'
---

Write integration test that forces a rekey by either waiting for the rekey interval timer or sending enough packets to trigger it. Verify the handshake count increases (new session negotiated). Verify data transfer continues uninterrupted across the rekey boundary -- send data before, during, and after rekey.