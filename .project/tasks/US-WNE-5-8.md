---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-5-8
points: 2
status: done
story_id: US-WNE-5
tags: []
title: Implement handshake initiation and timer event handling
updated: '2026-03-26'
---

Implement handshake flow: call Tunn::format_handshake_initiation() to start handshake, process handshake response via decapsulate(). Handle the TunnResult variants that indicate handshake packets need to be sent. Implement timer tick handling: call Tunn::update_timers() periodically and process resulting actions (send keepalive, initiate rekey, etc.). Track tunnel state (handshaking, established, idle).