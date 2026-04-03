---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-7-12
points: 1
status: done
story_id: US-WNE-7
tags: []
title: Implement wg_last_error() with thread-local storage
updated: '2026-03-26'
---

Implement a thread_local! RefCell<Option<CString>> that stores the most recent error message. Provide set_last_error(msg: &str) internal helper and #[no_mangle] extern "C" fn wg_last_error() -> *const c_char that returns the stored string or null if no error. Ensure the pointer remains valid until the next call on the same thread.