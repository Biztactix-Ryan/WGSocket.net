---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-51-6
points: 2
status: done
story_id: US-WNE-51
tags: []
title: Add zeroize crate and derive Zeroize/ZeroizeOnDrop on all Rust key structs
updated: '2026-04-03'
---

Add the zeroize crate as a dependency. Derive Zeroize and ZeroizeOnDrop on all structs containing key material: private keys, pre-shared keys, and session keys. Ensure WgDevice drop path triggers zeroization of all held key fields. Audit all Rust structs that hold cryptographic secrets and annotate them.