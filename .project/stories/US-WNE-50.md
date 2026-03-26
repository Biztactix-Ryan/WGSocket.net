---
acceptance_criteria:
- '.csproj configured with NuGet metadata: PackageId and Version and Description and
  Authors and License and RepositoryUrl'
- Native binaries included via runtimes/{rid}/native/ directory conventions with correct
  MSBuild Content items
- dotnet pack produces a self-contained .nupkg containing all 4 native binaries
- Package size is reasonable at approximately 8-16MB with 4 native binaries
- Package installs correctly in a fresh .NET 8 console project
- Consumer project can resolve and P/Invoke load the native library after install
  without manual steps
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-50
points: 3
priority: must
status: backlog
tags:
- nuget
- packaging
title: NuGet package configuration
updated: '2026-03-26'
---

As a package consumer, I want WgSocket published as a self-contained NuGet package with embedded native binaries so that dotnet add package WgSocket is the only step needed.