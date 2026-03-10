# ADR-007: Propulsion — Open Selection, ~3.5kg Thrust/Rotor at 6S

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q4: Propulsion](https://github.com/Arrow-air/project-quiver-mini/discussions/7)

## Decision

Motor selection is **not locked to a single model**. Quiver Mini v1 targets a performance spec: **~3.5kg thrust/rotor at 6S** (50% hover throttle at 7kg MTOW). The arm tip will use a universal or multi-option mount — not locked to one bolt pattern.

## Context

The original assumption was MAD 4x08 400KV (used in Kestrel). Community input during the design phase established that MAD 4x08 is insufficient for the 7kg MTOW ceiling.

## Performance Spec

| Parameter | Target |
|-----------|--------|
| Thrust per rotor | ~3.5kg at 6S (50% throttle) |
| Battery | 6S |
| Prop diameter | ~17–18" (driven by motor choice) |
| Configuration | Quad |

## Reference Motors (not locked)

| Motor | Max Thrust | Props | Weight | Notes |
|-------|-----------|-------|--------|-------|
| T-Motor MN5008 KV340 | ~4.2kg | 17–18" | 135g | 6S-rated, leading candidate |
| MAD 4x08 400KV | ~2.5kg | 15×4.8" | — | **Insufficient for 7kg ceiling** |

## Supply Chain Principle (deltaecho)

Before first build: document 2–3 validated motor options that satisfy the thrust, weight, and interface requirements. Avoid single-source dependency.

## Mount Design

- Universal/multi-option arm-tip interface
- "Design the motor mount adapter" is a natural early bounty — well-scoped, doesn't require the full frame to be complete

## Consequences

- Wheelbase will be driven by propulsion choice (~17–18" props → larger than Kestrel's 15" prop config)
- MAD 4x08 integrated arm sets are no longer the primary path (though MAD may offer larger options in this thrust range worth evaluating)
- Motor mount adapter becomes a community bounty
