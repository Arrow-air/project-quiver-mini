# Quiver Mini — Design Brief

This document summarizes the key design decisions for Quiver Mini. Decisions were made through community discussion in `#quiver-mini` on the Arrow Discord and are recorded in `docs/decisions/`.

**Last updated:** 2026-03-05  
**Status:** v1 spec locked — moving to design phase

---

## Locked In (Pre-Discussion)

These are inherited from Quiver or set by project goals:

| Decision | Value | Rationale |
|----------|-------|-----------|
| Attachment interface | Quiver-spec pogo-pin | Payload interoperability with Quiver |
| Flight controller PCB | Quiver FC PCB | Same firmware stack, same dev experience |
| Flight stack | ArduCopter | Proven, open-source |
| Battery system | 6S | Right voltage class for 5–10kg; Kestrel build confirms |
| Video/comms | SIYI camera + HM30 (likely) | Proven on Quiver; consistent ecosystem |
| Open source | Apache 2.0 | Yes |

---

## v1 Design Decisions (Locked March 2026)

Full rationale in `docs/decisions/`. Summary:

| # | Question | Decision | ADR |
|---|----------|----------|-----|
| Q1 | MTOW | **7kg** | [ADR-001](decisions/ADR-001-mtow.md) |
| Q2 | Enclosure | **Purpose-built smaller** | [ADR-002](decisions/ADR-002-enclosure.md) |
| Q3 | Frame | **Quad (4-motor X)** | [ADR-003](decisions/ADR-003-frame.md) |
| Q4 | Attachment | **Single bottom port, Quiver-compatible** | [ADR-004](decisions/ADR-004-attachment.md) |
| Q5 | Power-on | **Plug-in = on, XT90-S antispark** | [ADR-005](decisions/ADR-005-power-on.md) |
| Q6 | Arms | **CF tubes v1; printed beams tracked for v2** | [ADR-006](decisions/ADR-006-arms.md) |
| Q7 | Propulsion | **Open — ~3.5kg/rotor at 6S; universal arm-tip mount** | [ADR-007](decisions/ADR-007-propulsion.md) |
| Q8 | Use cases | **Sensor platform primary; docking station roadmap** | [ADR-008](decisions/ADR-008-use-cases.md) |

---

## Reference Builds

### Kestrel (Julius / far1no)
*Personal build, parallel to the community design. Informs v1 decisions.*

| Spec | Value |
|------|-------|
| MTOW | ~5kg |
| Configuration | Quad |
| Motors | MAD 4x08 400KV |
| Props | 15×4.8" |
| Battery | 6S, 22Ah recommended (~30min flight) |
| Body | Quiver enclosure |
| Electronics | Quiver Main PCB + FC PCB (DCDC swap for 6S) |
| Status | First flight completed Germany, March 2026 🇩🇪 |

---

## Design Principles

From community input during the discussion phase:

1. **Field maintainability:** 95% of maintenance tasks ≤15 min; all tools fit a backpack or car trunk. LRU philosophy. *(deltaecho)*
2. **Intentional design life:** ~100hr design life as a cost/weight lever. Allows smaller motors, printed parts, lower-grade bearings. Maintain 50% throttle hover safety margin. *(deltaecho)*
3. **Supply chain resilience:** Document 2–3 validated options for each critical component before first build. Avoid single-source dependency. *(deltaecho)*
4. **Manufacturing stack:** 3D printing + CF tubes + basic sheet metal + COTS fasteners. Accessible to builders without specialized tooling. *(deltaecho)*

---

## Next Steps

- [ ] Enclosure CAD (bounty)
- [ ] Motor mount adapter design (bounty — universal arm-tip interface)
- [ ] Validate T-Motor MN5008 KV340 and 2 alternatives at 6S
- [ ] Frame geometry / wheelbase calculation based on propulsion choice
- [ ] First-pass BOM
