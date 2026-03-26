---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-52-6
- US-WNE-52-7
- US-WNE-52-8
id: US-WNE-52-9
points: 1
status: todo
story_id: US-WNE-52
tags: []
title: Verify staleness detection catches a real change
updated: '2026-03-26'
---

Temporarily add a new #[no_mangle] pub extern "C" fn to the Rust source without regenerating the header. Run the staleness check script and verify it exits non-zero with the expected error message. Then regenerate the header and verify the check passes. Revert the temporary function.