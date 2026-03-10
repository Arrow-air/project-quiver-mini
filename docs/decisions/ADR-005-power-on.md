# ADR-005: Power-On Behavior — Plug-In = On

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q6: Power-On Behavior](https://github.com/Arrow-air/project-quiver-mini/discussions/5)

## Decision

Quiver Mini v1 will power on when the battery is connected. **XT90-S antispark connectors** will be used. No dedicated precharge circuit or power switch in v1.

## Rationale

- Unanimous community preference for simplicity in v1
- XT90-S antispark handles inrush current adequately for 6S at this power level
- Kestrel (Julius) validates this approach in practice
- A dedicated switch can be added in v2 if field operations require it
