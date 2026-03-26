---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-65-6
points: 1
status: todo
story_id: US-WNE-65
tags: []
title: Add cargo audit CI workflow (weekly + on PR)
updated: '2026-03-26'
---

Create a GitHub Actions workflow that runs `cargo audit` on every PR touching Cargo.toml/Cargo.lock and on a weekly cron schedule. Install cargo-audit via cargo install. Fail the workflow on any advisory. Ensure Cargo.lock is committed and tracked in git (add to .gitignore exclusion if needed).