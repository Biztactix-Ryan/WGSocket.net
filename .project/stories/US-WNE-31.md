---
acceptance_criteria:
- Namespace is WgSocket (not WgSocket.Net or WgSocket.Sockets)
- using WgSocket gives access to Socket and WgDevice and WgConfig and WgPeer and NetworkStream
- No naming conflicts with System.Net.Sockets when both namespaces are imported
- IntelliSense-friendly API surface with XML doc comments on all public members
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-31
points: 1
priority: must
status: done
tags:
- api
- namespace
- dx
title: Single-file import experience & namespace design
updated: '2026-03-27'
---

As a library consumer, I want a clean namespace design so that I can add a single `using WgSocket;` import and access all types without conflicts or confusion.