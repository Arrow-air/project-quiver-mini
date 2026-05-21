# Kestrel — Reference Build

- **Author:** Julius (far1no)
- **Status:** Flown; being documented as the practical near-term small platform/reference build
- **Weight class:** ~5kg MTOW

---

Kestrel is a personal build by Julius exploring a minimum viable small Quiver-class aircraft. Designed over a weekend hackathon in February 2026, it prioritizes maximum reuse of Quiver electronics to minimize new development.

After Kestrel's first flights, Arrow is treating it as the practical near-term small platform/reference build while clean-sheet Quiver Mini development is paused.

## Key Specs

| Item | Value |
|------|-------|
| Configuration | Quad (4-motor) |
| MTOW | ~5kg |
| Motors | MAD 4x08 Drone Arm Set 400KV |
| Props | 15×4.8" |
| Thrust (per motor) | ~2.5kg |
| Battery | 6S, 10–30Ah (22Ah recommended) |
| Target flight time | ~30 min (22Ah, no payload) |
| Body | Quiver enclosure (same lid, same footprint) |
| Arm tube diameter | 20mm |

## Electronics (Reused from Quiver)

- **Main PCB:** Quiver Main PCB (DCDC converters swapped for 6S-compatible versions)
- **FC PCB:** Quiver FC PCB (unchanged)
- **Camera:** SIYI gimbal camera
- **Video/comms:** HM30 air unit (located where Quiver's battery connector PCB was)
- **Sensors:** 360° LiDAR (top), 2× forward/rear radar, RPi (optional)

*DCDC converter swap requires a hot air gun and soldering experience.*

## Structure

- Foldable motor arm connectors (20mm tube)
- Carbon fiber thrust structure (X-pattern, same philosophy as Quiver)
- 3D printed enclosure + structure elements
- Landing gear integrated into MAD motor arms (foldable rod per arm — no separate landing gear assembly)
- Battery mounted under drone body with Velcro straps

## Power

- 6S LiPo (standard RC battery pack)
- Spark-free connector — drone powers on when battery is connected
- No separate battery connector PCB

## Attachment Interface

- Quiver-compatible attachment PCBs: left side, right side
- Bottom attachment port planned (not in CAD yet)

## What Kestrel Tells Us

- ✅ Quiver electronics stack works at 6S with a DCDC swap
- ✅ MAD 4x08 + 15" props is a viable propulsion choice for 5kg
- ✅ Quiver body size is functional (not optimal, but works)
- ✅ Integrated motor-arm landing gear is a clean solution
- ✅ First flights completed — use logs/build notes to inform any future Quiver Mini restart

## Files

*CAD files, logs, photos, and build notes to be added as they are cleaned up for publication.*
