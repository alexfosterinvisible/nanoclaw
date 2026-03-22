---
created: 2026-03-22T21:36:00.000Z
title: Verify statusline and ticket gate changes after CC restart
area: tooling
files:
  - ~/.claude/hooks/af-gsd-statusline.js
  - ~/.claude/hooks/ticket-gate.sh
  - ~/.claude/settings.json
---

## Problem

Several statusline and hook changes were made in session 19c7026d that require a CC restart to take effect. Need to verify they all work correctly:

1. Opus 4.6 [1m] model color is yellow (was red)
2. Ticket reference shows green when set, bold red "TICKET REQUIRED" when not
3. PROJ-123 style tickets are Cmd+clickable (links to ticket file)
4. Task label moved from line 1 to line 2 (after vintage)
5. ticket-gate.sh UserPromptSubmit hook fires and outputs SSID + ticket
6. SSID displayed after each prompt via hook output

## Solution

Restart CC and visually verify each item. Test:
- Start session without mentioning a ticket - should see red TICKET REQUIRED
- Mention #123 or PROJ-456 in prompt - should turn green
- Cmd+click the ticket - should open link
- Check task label is on line 2
- Check Opus 4.6 [1m] is yellow not red
