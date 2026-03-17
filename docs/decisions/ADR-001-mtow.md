# ADR-001: MTOW Target — 7kg

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q1: MTOW Target](https://github.com/Arrow-air/project-quiver-mini/discussions/1)

## Decision

Quiver Mini v1 will target a **7kg MTOW** (maximum takeoff weight).

## Context

The MTOW is the most consequential early decision — it drives frame geometry, motor selection, prop diameter, battery sizing, regulatory category, and cost. The initial assumption was 5kg (validated by the Kestrel reference build), but community input during the design discussion phase shifted this.

## Community Input

| Participant | Position | Rationale |
|-------------|----------|-----------|
| Julius (far1no) | 7kg | MAD 4x08 insufficient for 7kg; motors that support 7kg cost the same. Can still fly at 5kg payload. |
| Erick (errrks.eth) | 7kg | More platform flexibility; keeps the design from being too constrained. |
| Zeynep (ZeynepB) | 7kg | MAD 4x08 would hover at 7kg but suffer on speed and maneuverability. |
| Thomas (thomasg) | 7kg | Aligned with community after discussion; motor selection kept open. |

## Consequences

- Motor selection must target ~3.5kg thrust/rotor at 6S (see ADR-007)
- MAD 4x08 400KV is **not sufficient** for the 7kg ceiling (2.5kg max/rotor at 50% throttle)
- Frame geometry will be sized around the new propulsion system (~17–18" props, 25mm arm tubes)
- **Dry weight target: ≤3.0kg** (revised from 2.5kg after Hobbywing X6-SE selection; motor+ESC+prop: 1,392g)
- Payload budget: ~1.5–2kg usable after structural + electronics weight
- Regulatory: EU A3 category above 4kg; operators should plan accordingly

## Alternatives Considered

**5kg MTOW:** Validated by Kestrel. Lower cost, simpler regulatory path. Rejected in favor of flexibility and community consensus.
