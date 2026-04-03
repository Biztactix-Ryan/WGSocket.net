---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-17-6
points: 1
status: done
story_id: US-WNE-17
tags: []
title: Implement WgPeer configuration model
updated: '2026-03-26'
---

Create the WgPeer class in the WgSocket namespace with properties: PublicKey (byte[32]), Endpoint (IPEndPoint?), AllowedIPs (IReadOnlyList<IPNetwork>), PresharedKey (byte[]?), PersistentKeepalive (ushort?). Add constructor validation: PublicKey must be exactly 32 bytes, PresharedKey must be 32 bytes if provided, AllowedIPs must not be null. Support object initializer pattern. Override ToString() to redact key material (show first 4 chars + '...').