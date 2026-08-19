# Engineering-OS v1.8.0 — Migration Continuity Update

## Purpose

Synchronize active Engineering-OS documentation so future Atlas migrations do not confuse historical Archive records with current state.

## Applied Updates

- Active README source-of-truth precedence strengthened.
- FSOS current-state document synchronized from archived v1.0.37 to the current v1.1.x working line.
- Current Engineering-OS baseline explicitly retained as v1.7.0.
- Current MHC/Autopilot, Full PDF, legacy cleanup, Operations, and pending Mission Control state recorded.
- EL-004 added as a reusable engineering lesson for migration continuity.
- Historical Archive records intentionally left unchanged.

## Source-of-Truth Precedence

1. Active Engineering-OS root / active Core.
2. `02-Projects/<project>/` current project state.
3. `03-Knowledge/` current technology knowledge.
4. `04-Archive/` historical evidence only.

Archive version numbers and historical project states must never override active state.
