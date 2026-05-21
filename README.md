# Project Quiver Mini

A lighter, more accessible variant of the [Quiver](https://github.com/Arrow-air/project-quiver) open-source VTOL platform, developed by the [Arrow DAO](https://arrowair.com) community.

## What is Quiver Mini?

Quiver is a capable 25kg VTOL platform — but it's expensive and complex to build. Quiver Mini targets the 5–10kg class: approachable enough for a hobbyist to garage-build, capable enough for real light-commercial missions like aerial survey, inspection, and brush bullet dispersal.

**Design goals:**
- Significantly lower cost than Quiver
- Buildable by an individual with moderate electronics + fabrication skills
- Reuses Quiver's attachment interface (payloads are interchangeable)
- Reuses Quiver's FC PCB (same firmware stack, same development experience)
- ArduCopter-based, fully open-source

## Status

⏸️ **Paused / community-maintained** — Quiver Mini remains an open concept for a future purpose-built small Quiver platform, but Arrow is not actively managing clean-sheet Mini development right now.

Contributions, experiments, and design notes are still welcome. Expect slower review and less active coordination until the project is reprioritized.

Near-term small-platform work is shifting toward documenting and flying **Kestrel**, Julius's flown 5kg-class reference build that reuses existing Quiver electronics/PCBs.

## Reference Builds

| Build | Author | Status | Notes |
|-------|--------|--------|-------|
| [Kestrel](reference-builds/kestrel/) | Julius (far1no) | Flown | 5kg quad, MAD 4x08, 6S, Quiver body + Quiver PCBs |

Reference builds are community members' individual interpretations of the small-Quiver concept. Kestrel is being uploaded and documented separately as the practical near-term small platform/reference build; Quiver Mini remains the future clean-sheet design path.

## Repository Structure

```
project-quiver-mini/
├── docs/
│   ├── design-brief.md        # Preserved design direction and paused-project status
│   └── decisions/             # Log of design decisions and rationale
├── reference-builds/
│   └── kestrel/               # Julius's Kestrel reference build
└── src/                       # Official design files (CAD, firmware config, etc.)
```

## Contributing

This project is currently paused rather than actively coordinated. Join the Arrow Discord server and use `#quiver-mini` for design discussion, but please assume maintainers may be slow to respond.

Arrow DAO is an experiment in open, community-led hardware development. Contributions of all kinds are welcome: CAD, simulation, firmware, documentation, testing. For now, the most useful contributions are small, well-scoped notes, experiments, comparisons against Kestrel, or PRs that clearly improve the archived design direction without requiring heavy maintainer coordination.

## License

Hardware designs (CAD files, schematics, PCB layouts, manufacturing files) are licensed under the **[CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S v2)](LICENSE)**.

Software (firmware, scripts, tools) is licensed under the **[GNU General Public License v3.0 (GPL-3.0)](LICENSE-SOFTWARE)**.

Both licenses require that derivative works remain open source under the same terms.
