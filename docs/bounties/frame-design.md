# Bounty: Quiver Mini Frame Design

**Status:** Open  
**Repo:** [Arrow-air/project-quiver-mini](https://github.com/Arrow-air/project-quiver-mini)  
**Related ADRs:** ADR-001 (MTOW), ADR-003 (Quad), ADR-006 (Arms), ADR-007 (Propulsion)

---

## What we need

A CAD design for the Quiver Mini v1 frame — a quad frame for a 7kg MTOW sensor platform. The design should lean heavily into 3D printing for the structural body and hub, with 25mm carbon fiber tubes for the motor arms.

---

## Hard constraints

| Requirement | Value |
|---|---|
| Frame dry weight (no motors/electronics/battery) | ≤600g |
| MTOW rating | 7kg |
| Configuration | Quad |
| Motor arm tubes | **25mm CF round tube** (sourced off-the-shelf, not printed) |
| Prop clearance | 18" props (HF18×6.0") |
| Diagonal wheelbase | ~700–730mm (motor-to-motor) |
| Motor mount | Hobbywing X6-SE 25mm clamp (primary); T-Motor M3×4 bolt circle (secondary) |
| Attachment interface | Single bottom port, Quiver-compatible, centered on belly |
| CAN wiring | Cable routing channels from arm tubes into central hub |
| Power connector | XT90-S antispark, battery bay accessible without opening enclosure |

---

## Structure overview

The frame has two distinct material zones:

- **Arms:** 25mm CF round tubes — sourced standard, not printed. The Hobbywing X6-SE clamps directly to these.
- **Body/hub:** 3D printed — central chassis, arm clamps/joints, battery bay, electronics enclosure, landing gear. This is where the design work lives.

---

## Body/hub design preferences

- **Internal geometry:** Hollow structural forms where possible (not flat plates, not open U-channels). Internal ribbing and shell walls carry loads more effectively than solid infill.
- **Arm-to-body joint:** Interlocking geometry (dovetail or equivalent) to carry shear loads in the plastic geometry itself — secured with embedded hex nuts or heat-set inserts, not plastic threads
- **Electronics bay:** Designer defines the enclosure volume; PCB will be sized to fit. Document your interior dimensions clearly in the deliverables.
- **FC mount:** Provision for soft-mount (TPU standoffs or M3 boss for silicone gel pads)
- **Landing gear:** Integrated or bolt-on TPU printed legs; enough ground clearance for bottom attachment interface with compact payload (~80mm minimum clearance)
- **Arm fold:** Foldable arms preferred for transport
- **Motor mounts:** Must accommodate a 1.5mm thermal break washer (CF or aluminum) between motor base and plastic

## Print material guidance

- Body/hub: PET-CF or PA12-CF (structural, printable without heated chamber)
- Motor mount interface: PPA-CF or CF thermal break washer if using PET-CF
- Landing gear: 90A–95A TPU

## Fasteners

- Brass heat-set inserts (M3) for electronics mounting, cover panels, frequent-access joints
- Embedded hex nuts for arm-to-body structural joints
- No 3D-printed plastic threads in load-bearing locations

---

## Open to designer

- Body shape and proportions
- Lid/enclosure strategy (how electronics bay seals and opens)
- Arm fold mechanism design
- Number of printed pieces and assembly sequence
- Landing gear geometry
- Whether arm clamps are separate printed parts or integrated into the hub

---

## Deliverables

- CAD files (build123d Python preferred, or STEP + source files)
- Recommended slicer settings (wall count, infill type/density, material)
- Assembly notes (how it goes together, what hardware is needed)
- BOM for non-printed parts (tube lengths, clamp hardware, fasteners)
- Interior electronics bay dimensions

---

## Notes

- **Prototype path:** An off-the-shelf 650mm CF quad frame is acceptable as a parallel v0 prototype to validate electronics and propulsion before this custom frame is complete. This bounty is for the custom v1 frame.
- **PCB footprint:** Not yet defined — leave reasonable interior volume and document what you used. The PCB designer will size the board to fit.

## Resources

- [ADR-007: Propulsion (Hobbywing X6-SE specs)](decisions/ADR-007-propulsion.md)
- [Design brief](design-brief.md)
- [Kestrel reference build](../reference-builds/kestrel/README.md)
