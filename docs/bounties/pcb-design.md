# Bounty: Quiver Mini Main PCB Design

**Status:** Open  
**Reward:** 7,000 $ARROW  
**Repo:** [Arrow-air/project-quiver-mini](https://github.com/Arrow-air/project-quiver-mini)  
**Related ADRs:** ADR-001 (MTOW), ADR-002 (Enclosure), ADR-007 (Propulsion)

---

## What we need

A custom Main PCB for Quiver Mini v1. This replaces the full Quiver Main PCB with a 6S-native, purpose-sized board scaled for a 5–7kg sensor platform.

The Quiver Main PCB is a useful reference, but Quiver is 14S and 25kg — Mini needs a ground-up design sized for its weight class and form factor.

---

## Hard constraints

| Requirement | Value |
|---|---|
| Input voltage | 6S LiPo (22.2V nominal, ~25.2V max) |
| Max continuous input current | ≥80A (4× motors, peaks to 20A+ per motor) |
| Board outline | Fit within **~180×120mm** (see frame bounty interior spec: 190×130mm minimum bay) |
| Mounting pattern | 4× M3 standoffs, compatible with FC PCB stack (30.5×30.5mm or 45×45mm patterns) |
| Motor interface | 4× DSHOT/PWM ESC signal outputs for v1; optional 4× CAN headers/pads for future Hobbywing telemetry |
| Power output — CAN bus | 5V regulated, ≥500mA |
| Power output — avionics | 5V, ≥3A (Flight controller, companion computer) |
| Power output — payloads | 5V and 12V rails for the single bottom attachment interface PCB |
| Battery connector | XT90-S (antispark) |
| ESC architecture | 4× individual integrated ESC/motor assemblies; DSHOT/PWM primary for v1, CAN optional/future |

---

## Functional requirements

### Power distribution
- Main 6S bus distribution to 4× motor outputs (direct battery voltage, no conversion)
- No dedicated pre-charge circuit for v1; use XT90-S antispark per ADR-005
- Polarity protection
- Blade fuses or PTC protection on regulated rails
- Voltage and current monitoring on main bus (for ArduPilot BATTERY monitor — compatible IC preferred: INA226 or INA3221)

### ESC signal and CAN bus
- 4× DSHOT/PWM motor signal outputs as the v1 baseline for ArduPilot compatibility and lower integration risk
- CAN remains a preferred future/optional path for Hobbywing telemetry; include connector pads or documented expansion path if feasible
- CAN bus available for peripherals (GPS, rangefinder, LIDAR)
- 120Ω termination resistors, selectable via jumper where CAN is implemented

### FC interface
- Standard ArduPilot Pixhawk connector pinout
- UART breakout headers: minimum 4× UARTs for GPS, telemetry, payload serial, spare
- I2C breakout (for compass, barometer)
- ADC input for battery voltage/current passthrough to FC

### Attachment interface
- 1× bottom attachment port connector matching the Quiver pogo-pin PCB footprint
- 5V and 12V switched power to the attachment port (enable via FC GPIO or dedicated power switch IC)
- UART passthrough to the attachment port minimum; CAN preferred if routing/connector budget allows

### Indicators & connectors
- Power LED (board live indicator)
- ARM/DISARM LED output header (for external LED)
- USB-C passthrough for FC firmware flashing (optional but preferred)
- JST-GH standard for signal connectors

---

## Out of scope (separate PCBs or future work)

- Flight controller (use standard Pixhawk 6C/6X)
- Attachment interface PCB (Quiver's existing design is reused)
- GPS/compass (external unit)
- FPV/video distribution

---

## Stackup target

**6-layer, 2mm FR4** — This is the recommended default, not left fully open.

- **6 layers** — gives adequate separation between power planes, signal layers, and ground pours. Better EMI performance than 4-layer at this board complexity. JLCPCB supports 6-layer at reasonable cost.
- **2mm thickness** — ~2× stiffer in bending vs standard 1.6mm. On a ~180×120mm board carrying heavy components (capacitors, connectors, MOSFETs), the extra rigidity reduces solder joint fatigue from motor vibration. This is a meaningful improvement for drone applications.
- **Stackup guidance:** With 6 layers in 2mm you get better dielectric separation between signal and plane layers vs cramming 6 layers into 1.6mm — cleaner controlled-impedance routing and better plane isolation by default.

Deviations from this target are acceptable with justification in the design notes.

---

## Open to designer

- Connector placement and orientation
- Thermal relief strategy for high-current traces
- Optional: onboard IMU, barometer, or buzzer driver
- Component selection within spec (preferred: JLCPCB-stocked or common DigiKey/Mouser parts for buildability)

---

## Deliverables

- KiCad project files (schematic + layout), committed to repo
- Gerber files + drill files ready for JLCPCB or equivalent fab
- Schematic PDF for review
- BOM (CSV format, with LCSC/DigiKey part numbers where available)
- Basic assembly notes (any tricky parts, special order items, hand-soldering requirements)
- Estimated fab+assembly cost for 10 units at JLCPCB (PCBA quote screenshot acceptable)

---

## Reference

- [ADR-007: Propulsion (Hobbywing X6-SE specs)](../decisions/ADR-007-propulsion.md)
- [ADR-002: Enclosure](../decisions/ADR-002-enclosure.md)
- [Frame design bounty](frame-design.md) — interior bay dimensions are defined there; PCB must fit within that envelope
- [Design brief](../design-brief.md)
- Quiver Main PCB (existing full Quiver design) — available in project-quiver repo as reference; adapt for 6S, do not copy directly

---

## Notes

- Coordinate with the frame designer on exact board outline — the 180×120mm target comes from the frame bounty interior spec (190×130mm bay) with margin. If you take the frame bounty first, define your interior dimensions and the PCB designer will size to fit.
- Erick (<@421500183524671490>) is the primary point of contact for PCB questions and review.
- Target fab: JLCPCB PCBA for first batch.

