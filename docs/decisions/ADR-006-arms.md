# ADR-006: Arm Construction — Carbon Fiber Tubes (v1)

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q8: Arm Construction](https://github.com/Arrow-air/project-quiver-mini/discussions/10)

## Decision

Quiver Mini v1 will use **carbon fiber tubes** for arm construction. Printed structural beams are tracked for v2.

## Context

The two candidates were CF tubes (traditional) and 3D-printed structural beams (Voron-style, championed by KBM).

## Rationale

**CF tubes (v1):**
- Thomas: CF tubes have held up in Quiver crashes; it's connectors that break, not tubes
- MAD-style motors use tube-clamp mounts — CF tubes avoid a custom motor mount adapter in v1
- Globally sourceable, well-understood, easy to replace
- KBM's FEA work on printed beams showed viability but also constraints (printer bed size limits, harder to simulate, slightly heavier)

**V2 path (printed structural beams):**
- Explicitly tracked for v2, especially if motor selection moves to a flat-mount design
- KBM's work is valuable and will feed directly into the next iteration
- deltaecho's supply chain principle applies: 3D printing + CF tubes + basic sheet metal + COTS fasteners covers all categories without specialized tooling

## Consequences

- Standard CF tube sizing TBD based on motor/prop geometry (likely 16–20mm OD)
- Arm connector design is a key early deliverable — crash-critical interface
