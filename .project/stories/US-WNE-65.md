---
acceptance_criteria:
- cargo audit runs in CI (weekly scheduled + on PR)
- Cargo.lock committed and pinned
- Dependabot configured for Cargo.toml and .csproj
- Dependabot PRs for native deps flagged for manual review (not auto-merged)
- dotnet list package --vulnerable in CI
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-65
points: 2
priority: should
status: backlog
tags:
- security
- ci
- dependencies
title: Dependency security scanning
updated: '2026-03-26'
---

As a security engineer, I want automated CVE monitoring for all Rust and .NET dependencies so that known vulnerabilities are detected early and dependency updates are reviewed before merging.