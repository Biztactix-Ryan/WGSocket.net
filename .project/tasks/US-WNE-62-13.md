---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-13
points: 1
status: todo
story_id: US-WNE-62
tags: []
title: Add CI workflow for nightly/on-demand fuzz runs
updated: '2026-03-26'
---

Create a GitHub Actions workflow that runs cargo-fuzz targets on a nightly schedule and on-demand via workflow_dispatch. Configure appropriate time limits per target (e.g. 10 minutes each). Archive any crash artifacts. Fail the workflow if any target finds a crash. Add badge to README.