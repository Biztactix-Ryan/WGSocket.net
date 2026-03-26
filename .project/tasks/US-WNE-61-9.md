---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-61-7
id: US-WNE-61-9
points: 2
status: todo
story_id: US-WNE-61
tags: []
title: Add GitHub Pages deployment and CI doc generation
updated: '2026-03-26'
---

Create a GitHub Actions workflow (.github/workflows/docs.yml) that runs on release tags: checks out code, installs docfx, builds the API reference, and deploys to GitHub Pages using the gh-pages branch. Configure the repo GitHub Pages settings documentation. Add a badge or link in README.md pointing to the hosted docs site.