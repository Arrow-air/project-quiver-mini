# ADR-003: Frame Architecture — Quad

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q3: Frame Architecture — Quad or X8?](https://github.com/Arrow-air/project-quiver-mini/discussions/3)

## Decision

Quiver Mini v1 will use a **quad (4-motor X) configuration**.

## Context

The two candidates were quad (4-motor) and X8 (8-motor coaxial). Quiver full-size uses X8 for redundancy.

## Vote Summary

Thomas, Julius, Erick, Zeynep: quad. KBM: any works (noted hex has better space utilization).

## Rationale

- Simplicity and lower parts cost are appropriate for this weight class
- Motor redundancy at 7kg is less critical than at 25kg — sensor platform missions can tolerate a controlled autoland
- Consistent with Kestrel reference build
- X8 or hex remains a natural v2 path if requirements grow

## Consequences

- 4 motors, 4 ESCs; simpler power distribution and wiring
- No single-motor-failure survivability — mission planning should account for this
