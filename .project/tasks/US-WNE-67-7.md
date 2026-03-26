---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-67-7
points: 1
status: todo
story_id: US-WNE-67
tags: []
title: Document approved dependencies and review process in SECURITY.md
updated: '2026-03-26'
---

Add a section to SECURITY.md listing all approved dependency versions for security-critical crates (boringtun, smoltcp, zeroize, etc.) with their pinned versions and expected checksums. Document the review process for dependency version bumps: who reviews, what checks are required (changelog review, diff audit, CVE check), and how the checksums file is updated.