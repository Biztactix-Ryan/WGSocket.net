---
acceptance_criteria:
- Rust side uses zeroize crate on all key fields (private key and PSK and session
  keys)
- Key material zeroed when WgDevice is dropped
- C# side uses fixed/pinned buffers and explicit zeroing for key parameters
- 'Verify with test: dump memory region after dispose and confirm keys are zeroed'
- Debug output (Display/Debug traits) never includes key material
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-51
points: 3
priority: must
status: backlog
tags:
- security
- zeroization
- mvp
title: Key material zeroization
updated: '2026-03-26'
---

As a security engineer, I want all key material (private keys, PSKs, session keys) to be securely zeroed from memory upon disposal so that sensitive cryptographic secrets cannot be recovered from process memory after use.