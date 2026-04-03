---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-3-6
points: 1
status: done
story_id: US-WNE-3
tags: []
title: Implement INI-style line tokenizer
updated: '2026-03-26'
---

Create a tokenizer/lexer in config.rs (or a config/parser.rs submodule) that reads wg.conf content line by line and classifies each line as: SectionHeader (e.g. [Interface], [Peer]), KeyValue (e.g. PrivateKey = abc123), Comment (# lines), or Blank. Strip whitespace and handle '=' with optional surrounding spaces. Track line numbers for error reporting. Return a Vec of typed tokens with line number metadata.