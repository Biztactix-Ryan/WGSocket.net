---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-14-6
id: US-WNE-14-7
points: 1
status: todo
story_id: US-WNE-14
tags: []
title: Implement wg_device_new_from_struct with WgConfig FFI struct
updated: '2026-03-26'
---

Define a #[repr(C)] WgConfig struct with fields for private_key, listen_port, peer_public_key, peer_endpoint, peer_allowed_ips, and tunnel_address. Implement #[no_mangle] extern "C" fn wg_device_new_from_struct(config: *const WgConfig) -> i64 that validates the struct pointer, converts fields, creates a WgDevice, and returns a handle. Null pointer returns WG_ERR_INVALID_CONFIG.