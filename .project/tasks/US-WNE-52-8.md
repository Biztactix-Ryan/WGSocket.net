---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-52-8
points: 1
status: todo
story_id: US-WNE-52
tags: []
title: Integrate cbindgen check into CI workflow
updated: '2026-03-26'
---

Add a step in the CI workflow (ci.yml) that runs the header staleness check. This should run in one of the Linux matrix legs (or as a separate job) before the build step. Install cbindgen via cargo install cbindgen or use a cached version. Fail the build if the header is out of date.