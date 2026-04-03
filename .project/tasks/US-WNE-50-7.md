---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-50-7
points: 1
status: done
story_id: US-WNE-50
tags: []
title: Configure NuGet metadata in WgSocket.csproj
updated: '2026-03-29'
---

Add PropertyGroup to WgSocket.csproj with: PackageId=WgSocket, Version (matching Cargo.toml), Description, Authors, PackageLicenseExpression (MIT or as appropriate), RepositoryUrl pointing to GitHub repo, PackageProjectUrl, PackageTags (wireguard, networking, vpn, native), PackageReadmeFile=README.md. Include README.md as PackageFile. Set GeneratePackageOnBuild=false (pack is explicit).