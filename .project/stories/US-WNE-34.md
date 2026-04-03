---
acceptance_criteria:
- Test device free releases all sockets
- Test no memory leaks after create/use/free cycle (valgrind or similar)
- Test key material is zeroed after device free
- Test I/O thread terminates after device free
- Test handle map doesn't grow unboundedly after repeated create/free
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-34
points: 2
priority: must
status: done
tags:
- rust
- testing
- resource-management
- safety
title: Resource cleanup and leak tests
updated: '2026-03-28'
---

As a developer, I want tests that verify resource cleanup and absence of memory leaks so that I can ensure the library safely frees all resources, zeroes sensitive key material, and handles repeated create/free cycles without handle map growth.