# Bounty: Quiver Mini Frame Design

**Status:** Open  
**Repo:** [Arrow-air/project-quiver-mini](https://github.com/Arrow-air/project-quiver-mini)  
**Related ADRs:** ADR-001 (MTOW), ADR-003 (Quad), ADR-006 (Arms), ADR-007 (Propulsion)

---

## What we need

A CAD design for the Quiver Mini v1 frame — a 3D-printable quad frame for a 7kg MTOW sensor platform. The design should be buildable by a hobbyist with a prosumer FDM printer and basic CF tube/hardware sourcing.

---

## Hard constraints

| Requirement | Value |
|---|---|
| Frame dry weight (no motors/electronics/battery) | ≤500g |
| MTOW rating | 7kg |
| Configuration | Quad |
| Motor arm tubes | **25mm CF round tube** |
| Prop clearance | 18" props (HF18×6.0") |
| Diagonal wheelbase | ~700–730mm (motor-to-motor) |
| Motor mount | Hobbywing X6-SE clamp pattern (primary); T-Motor M3×4 bolt circle (secondary) |
| Attachment interface | Single bottom port, Quiver-compatible, centered on belly |
| CAN wiring | Channels for CAN bus cable routing through arms to central hub |
| Power connector | XT90-S antispark, battery bay accessible without opening enclosure |

## Strong preferences

- **Arm geometry:** Hollow rectangular or octagonal cross-section where printed — not flat plates, not open U-channels
- **Arm-to-body joint:** Interlocking geometry (dovetail or equivalent) to carry shear loads, secured with embedded hex nuts or heat-set inserts — not plastic threads
- **Electronics bay:** Designer defines the enclosure volume; PCB will be designed to fit. Note your interior dimensions clearly so Erick can design the board to fit.
- **FC mount:** Provision for soft-mount (TPU standoffs or M3 boss for silicone pads)
- **Landing gear:** Integrated or bolt-on TPU printed legs at arm roots; enough ground clearance for the bottom attachment interface with a compact payload attached (~80mm minimum)
- **Fold:** Arms foldable for transport (foldable arm clamps or integrated fold joint)
- **Print material:** Target PET-CF or PA12-CF for structural parts; motor mounts in PPA-CF or with 1.5mm CF thermal break washer between motor and plastic
- **Fasteners:** Brass heat-set inserts (M3) for avionics and cover panels; embedded hex nuts for arm-to-body structural joints

## Open to designer

- Body shape and proportions
- Lid/enclosure strategy (how electronics bay seals and opens)
- Arm fold mechanism design
- Number of printed pieces and assembly sequence
- Exact landing gear geometry

## Deliverables

- CAD files (build123d Python preferred, or STEP + source files)
- Recommended slicer settings (wall count, infill type/density, material)
- Basic assembly notes (how it goes together, what hardware is needed)
- BOM for non-printed parts (tube lengths, clamp hardware, fasteners)

## Notes

- **Prototype path:** An off-the-shelf 650mm CF quad frame (e.g. Tarot T810 or equivalent) is acceptable as a parallel v0 prototype to validate electronics and propulsion before the custom frame is complete. The bounty is for the custom v1 frame.
- **PCB footprint:** Not yet defined — leave reasonable interior volume (~200×150mm minimum) and document what you used. Erick will design the PCB to fit.
- **Reference material:** [3D printed UAV research summary](../research/3d-printed-uav-research.md) — covers material selection, arm geometry, thermal management, and fastening best practices.

## Resources

- [ADR-007: Propulsion (Hobbywing X6-SE specs)](decisions/ADR-007-propulsion.md)
- [Design brief](design-brief.md)
- [Kestrel reference build](../reference-builds/kestrel/README.md)
