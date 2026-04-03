---
acceptance_criteria:
- Private key and PSK fields never appear in log output at any level (Trace through
  Critical)
- 'Test: enable all log levels and perform full lifecycle and grep logs for key material
  — must find nothing'
- Structured logging fields for keys are redacted
- Code review checklist item for no-log enforcement documented
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-59
points: 2
priority: must
status: done
tags:
- security
- logging
title: No-log enforcement for secrets
updated: '2026-04-03'
---

As a security engineer, I want to guarantee that private keys and pre-shared keys never appear in log output at any level (Trace through Critical) so that sensitive key material cannot leak through application logs, diagnostics, or telemetry.