---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-9-7
points: 1
status: done
story_id: US-WNE-9
tags: []
title: Declare peer and key management P/Invoke methods
updated: '2026-03-26'
---

Add LibraryImport declarations for wg_peer_add, wg_peer_remove, wg_peer_list, wg_generate_keypair, and wg_last_error in NativeMethods.cs. Key parameters are byte* with fixed 32-byte length. wg_last_error returns a UTF-8 string pointer. Use [return: MarshalAs(...)] where needed.