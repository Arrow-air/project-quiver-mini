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

🟡 **Design phase** — community discussion open. See [`docs/design-brief.md`](docs/design-brief.md) for open questions.

## Reference Builds

| Build | Author | Status | Notes |
|-------|--------|--------|-------|
| [Kestrel](reference-builds/kestrel/) | Julius (far1no) | Parts ordered | 5kg quad, MAD 4x08, 6S, Quiver body |

Reference builds are community members' individual interpretations of the Quiver Mini concept. They inform the official design but are not the spec.

## Repository Structure

```
project-quiver-mini/
├── docs/
│   ├── design-brief.md        # Open design questions for community discussion
│   └── decisions/             # Log of design decisions and rationale
├── reference-builds/
│   └── kestrel/               # Julius's Kestrel reference build
└── src/                       # Official design files (CAD, firmware config, etc.)
```

## Contributing

This project is coordinated through the Arrow Discord server — join `#quiver-mini` to participate in design discussions.

Arrow DAO is an experiment in open, community-led hardware development. Contributions of all kinds are welcome: CAD, simulation, firmware, documentation, testing.

## License

Hardware designs (CAD files, schematics, PCB layouts, manufacturing files) are licensed under the **[CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S v2)](LICENSE)**.

Software (firmware, scripts, tools) is licensed under the **[GNU General Public License v3.0 (GPL-3.0)](LICENSE-SOFTWARE)**.

Both licenses require that derivative works remain open source under the same terms.
