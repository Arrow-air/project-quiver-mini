# Quiver Mini — Design Brief

This document frames the key design decisions for Quiver Mini. Each question is open for community input in `#quiver-mini` on the Arrow Discord. Decisions will be logged in `docs/decisions/` as they're made.

**Last updated:** 2026-02-26  
**Status:** Open for community discussion

---

## What We Know (Locked In)

These are not up for debate — they're inherited from Quiver or set by project goals:

| Decision | Value | Rationale |
|----------|-------|-----------|
| Attachment interface | Quiver-spec | Payload interoperability with Quiver |
| Flight controller PCB | Quiver FC PCB | Same firmware stack, same dev experience |
| Flight stack | ArduCopter | Proven, open-source |
| Battery system | 6S (validated) | Right voltage class for 5–10kg; Julius's Kestrel build confirms it works |
| Video/comms | SIYI camera + HM30 | Proven on Quiver; consistent ecosystem |
| Open source | Yes | Apache 2.0 |

---

## Open Questions

### 1. MTOW Target: 5kg or 7kg?

This is the most important decision — it drives frame size, motor choice, prop diameter, battery capacity, and ultimately cost and regulatory category.

**5kg**
- ✅ Julius's Kestrel proves this is achievable with the Quiver electronics stack
- ✅ Lower cost; easier to transport
- ✅ EU category A2 (below 4kg without remote ID) / simpler regulatory pathway in many jurisdictions
- ❌ Leaves less payload margin after structural + electronics weight
- ❌ Brush bullet or heavier sensor payloads may push limits

**7kg**
- ✅ More payload margin (~1.5–2kg usable payload)
- ✅ Can handle heavier attachments (larger multispectral, brush bullet at full capacity)
- ❌ Larger motors/props = higher cost
- ❌ More complex regulatory category in EU (A3 above 4kg)
- ❌ Less "hobbyist accessible"

**Community question:** What's the primary use case you're designing for? Survey (lighter sensors, lower MTOW fine) or payload operations (brush bullet, heavier sensors)?

---

### 2. Body / Enclosure Size

**Option A: Keep Quiver body dimensions** (Julius's Kestrel approach)
- ✅ Reuses Quiver lid, enclosure, Main PCB without redesign
- ✅ Faster to first build
- ❌ Body is oversized for the propulsion system — visually "top-heavy"
- ❌ Doesn't feel purpose-built; harder to shrink later

**Option B: Purpose-built smaller enclosure**
- ✅ Better proportioned; more "Mini" feel
- ✅ Opportunity to simplify enclosure (fewer features needed for lighter weight class)
- ❌ Requires new enclosure CAD
- ❌ May require Main PCB layout changes (DCDC, connectors repositioned)

**Community question:** Is electronics reuse worth the larger body, or do we want to design a proper Mini-sized enclosure?

---

### 3. Frame Architecture

**Quad (4-motor)** — Kestrel approach
- ✅ Simpler; fewer motors/ESCs to tune
- ✅ Lower parts cost
- ❌ No motor redundancy (one failure = crash)
- ❌ Less efficient at carrying heavy payloads

**X8 (4-arm, 8-motor coaxial)** — Quiver approach
- ✅ One motor failure survivable
- ✅ More efficient for heavier loads
- ❌ More expensive; more complex wiring
- ❌ Overkill for 5kg class?

**Community question:** Is motor redundancy worth the added cost and complexity at this weight class?

---

### 4. Propulsion System

Julius's Kestrel uses **MAD 4x08 400KV** with 15x4.8" props (2.5kg thrust each, ~5kg MTOW as quad).

**Community question:** Should we validate the MAD 4x08 as the standard, or evaluate alternatives (T-Motor, Hobbywing all-in-one, etc.)?

Things to evaluate:
- Cost (MAD vs alternatives)
- Availability (can a builder source this globally?)
- Integrated landing gear (MAD's foldable rod is elegant — does any alternative offer this?)
- Repairability

---

### 5. Attachment Interface Placement

Quiver has attachment PCBs on the sides. Julius's Kestrel adds a bottom attachment point (not in CAD yet).

**Community question:**
- How many attachment ports? (Left, right, bottom — or simplify to fewer?)
- Should bottom attachment be standard, or an optional upgrade?
- Any use cases that require top attachment?

---

### 6. Battery Connector / Power-On Behavior

Julius's Kestrel uses a spark-free connector — the drone powers on as soon as the battery is connected. Quiver uses a dedicated battery connector PCB with a separate power switch.

**Community question:** Is the simplified "plug in = power on" approach acceptable for Mini, or do we want a dedicated power switch for safety/convenience?

---

## Reference Builds

### Kestrel (Julius / far1no)
*Personal build, informing Quiver Mini design*

| Spec | Value |
|------|-------|
| MTOW | ~5kg |
| Configuration | Quad |
| Motors | MAD 4x08 400KV |
| Props | 15x4.8" |
| Battery | 6S, 10–30Ah (22Ah recommended, ~30min flight) |
| Body | Quiver enclosure (same lid) |
| Electronics | Quiver Main PCB + FC PCB (DCDC converter swap for 6S) |
| Landing gear | Integrated into MAD motor arms (foldable rod) |
| Status | Parts ordered, first build in progress (Feb 2026) |

---

## How to Contribute

1. Join `#quiver-mini` on the Arrow Discord
2. React to or comment on the open questions above
3. Share relevant experience, reference designs, or calculations
4. Volunteer for a workstream when the design converges

All input — even "I think option A is better because..." — is valuable. You don't need CAD skills to contribute to this phase.
