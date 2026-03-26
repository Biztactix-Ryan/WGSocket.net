---
created: '2026-03-26'
id: EPIC-WNE-8
points: null
priority: must
status: draft
tags:
- testing
- integration
- mvp
target_date: null
title: End-to-End Integration Tests
updated: '2026-03-26'
---

Full-stack integration tests proving the library achieves its goals. Spin up two WgDevice instances with generated keypairs on localhost UDP, perform real Noise_IKpsk2 handshakes, and validate: TCP echo roundtrip through the encrypted tunnel, bidirectional data transfer, multi-peer scenarios, AllowedIPs enforcement (packets outside allowed range are dropped), automatic rekey after timer expiry, concurrent socket operations, large payload transfer, and throughput benchmarks. Also test interop with a real wireguard-go or kernel WireGuard peer if available in CI.