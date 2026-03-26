---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-35-6
points: 2
status: todo
story_id: US-WNE-35
tags: []
title: Implement global handle map with opaque usize handles
updated: '2026-03-26'
---

Create a HandleMap using a global static Mutex<HashMap<usize, Arc<WgDevice>>> or a lock-free slab allocator. Assign monotonically increasing usize handles (or use the Box pointer address). Provide insert(device) -> usize, get(handle) -> Option<Arc<WgDevice>>, and remove(handle) -> Option<Arc<WgDevice>> operations. The handle is the only thing that crosses the FFI boundary -- no raw pointers exposed to C callers. Use a generation counter or similar to prevent ABA problems on handle reuse.