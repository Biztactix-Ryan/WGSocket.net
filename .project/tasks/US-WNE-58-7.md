---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-58-7
points: 1
status: todo
story_id: US-WNE-58
tags: []
title: Configure .csproj for XML documentation generation
updated: '2026-03-26'
---

Update WgSocket.csproj to set GenerateDocumentationFile=true and TreatWarningsAsErrors for CS1591 (missing XML comment warnings) in a PropertyGroup. This ensures any public member without XML docs causes a build failure, enforcing complete documentation coverage. Verify the XML doc file is produced in the output directory on build.