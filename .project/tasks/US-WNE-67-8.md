---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-67-8
points: 1
status: todo
story_id: US-WNE-67
tags: []
title: Configure CVE alerting for pinned dependencies
updated: '2026-03-26'
---

Ensure GitHub security advisories and Dependabot alerts are enabled for the repository. Configure notification routing so that CVEs affecting pinned crates trigger immediate team notification (via GitHub notification settings or a webhook to Slack/Discord). Verify alerts fire for both Cargo and NuGet ecosystems.