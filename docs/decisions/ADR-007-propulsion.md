# ADR-007: Propulsion — Hobbywing X6-SE 380KV (Primary)

**Status:** Accepted  
**Date:** 2026-03-17 (updated from 2026-03-05)  
**Discussion:** [Design Q4: Propulsion](https://github.com/Arrow-air/project-quiver-mini/discussions/7)

## Decision

**Primary motor: Hobbywing X6-SE 380KV** with HF18×6.0" prop.

Motor selection is not locked — builders may substitute from the validated alternatives list below — but the Hobbywing X6-SE is the reference configuration for frame design, PCB layout, and parameter files.

## Rationale

- **5.5kg max thrust/rotor** → 3.1:1 T/W at 7kg MTOW; hovers at ~32% throttle
- **Integrated motor+ESC+prop** — one BOM item, clean install, no ESC compatibility questions
- **CAN protocol** — individual motor RPM telemetry, ESC health monitoring, voltage/current per motor in ArduPilot; valuable for a serious sensor platform
- **Hobbywing ecosystem** — Arrow team has existing experience with Hobbywing X-series on full Quiver; spare parts, troubleshooting knowledge carry over
- **6S compatible** ✅
- **~$70-80/unit** — competitive

The ~400g weight premium over lighter alternatives is accepted. Dry weight target is revised to **≤3.0kg** (from 2.5kg) to reflect this.

## Performance Spec

| Parameter | Target | Hobbywing X6-SE |
|-----------|--------|-----------------|
| Thrust per rotor | ≥3.5kg at 6S | **5.5kg max** ✅ |
| Hover throttle (7kg MTOW) | ≤60% | **~32%** ✅ |
| Battery | 6S | 6S ✅ |
| Prop diameter | 17–18" | HF18×6.0" ✅ |
| CAN telemetry | preferred | ✅ |

## Reference Configuration

| Parameter | Value |
|-----------|-------|
| Motor | Hobbywing X6-SE 380KV |
| Prop | HF18×6.0" (included) |
| ESC | Integrated |
| Weight (motor+ESC+prop) | 348±5g per unit |
| Arm tube diameter | **25mm** |
| Max power | 1057W |
| Recommended thrust/rotor | 2–2.5kg |
| Max thrust/rotor | 5.5kg |
| CAN protocol | Yes |
| Price (est.) | ~$70–80/unit |

**Note:** Arm tube diameter is 25mm — frame spec must use 25mm CF tubes, not 20mm.

## Validated Alternatives

| Motor | Max Thrust | Weight (all-in) | Arm Tube | CAN | ~Price | Notes |
|-------|-----------|-----------------|----------|-----|--------|-------|
| **Hobbywing X6-SE 380KV** ✅ | 5.5kg | 348g | 25mm | ✅ | ~$75 | **Primary** |
| T-Motor MN5008 KV340 | 4.2kg | ~270g (motor+ESC+prop) | 19mm bolt | ❌ | ~$120 | Confirmed backup |
| SunnySky X4110S KV400 | ~3.0–3.5kg (est.) | 187g motor | — | ❌ | ~$40 | Needs bench validation |

## Supply Chain Principle (deltaecho)

Document 2–3 validated options before first build. Motor mount adapter at the arm tip must accommodate at minimum the Hobbywing 25mm clamp pattern and the T-Motor M3×4 bolt pattern.

## Frame Implications

- **Arm tube: 25mm CF round tube** (revised from 20mm)
- Wheelbase: ~700–730mm diagonal (18" props)
- Motor mount adapter bounty: accommodate Hobbywing + T-Motor mount patterns
- Dry weight target revised to **≤3.0kg**

## Consequences

- CAN bus wiring must be routed through arms to central PCB
- PCB must include CAN interface (or FC handles CAN passthrough)
- Heavier propulsion system than originally estimated — enclosure and arm design must account for this
