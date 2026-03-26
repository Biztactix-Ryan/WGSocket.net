---
acceptance_criteria:
- Cargo.lock committed with pinned versions
- Verify boringtun and smoltcp crate checksums
- Document approved dependency versions in SECURITY.md
- Alerting on new CVEs for pinned dependencies
- Review process for dependency version bumps documented
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-67
points: 2
priority: should
status: backlog
tags:
- security
- supply-chain
- dependencies
title: Supply chain hardening
updated: '2026-03-26'
---

As a security engineer, I want pinned dependency versions with checksum verification and a documented review process so that supply chain attacks through compromised or substituted crate versions are prevented.