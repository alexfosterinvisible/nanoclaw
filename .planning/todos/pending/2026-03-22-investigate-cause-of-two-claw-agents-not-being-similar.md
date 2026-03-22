---
created: 2026-03-22T21:34:59.189Z
title: Investigate cause of two claw agents not being similar
area: general
files: []
---

## Problem

Two claw agents are exhibiting different behavior or configuration despite being expected to be similar/identical. Root cause is unknown - needs investigation into what diverged between them (config, container build, group CLAUDE.md, skills loaded, etc.).

## Solution

TBD - needs investigation. Likely areas to check:
- Per-group CLAUDE.md differences
- Container build state / cached layers
- Channel-specific config or credentials
- Skill loading order or availability
