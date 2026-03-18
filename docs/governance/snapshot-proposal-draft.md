# Snapshot Proposal Draft: Quiver Mini v1 Development Fund

**Status:** Draft — not yet submitted  
**Proposed by:** thomasg  
**Amount requested:** 25,000 $ARROW  
**Target wallet:** TBD

---

## Summary

Allocate **25,000 $ARROW** to fund the technical development bounties required to bring Quiver Mini v1 from locked design decisions to a documented, repeatable first build.

Quiver Mini is an Arrow community project to build a smaller, lighter Quiver variant — a 7kg MTOW open-source quad drone optimized for sensor payloads (cameras, LiDAR, thermal, multispectral). The project repo is live, design decisions are locked, and the first technical bounties are ready to post. This proposal funds the bounty pool.

---

## Background

The Quiver Mini project was initiated in February 2026 to build a platform in the 5–10kg class that:
- Uses the Quiver attachment interface standard (payload interoperability)
- Runs ArduCopter on the Quiver FC PCB
- Is garage-buildable with accessible components
- Serves as an experiment in AI-human open source collaboration

Key design decisions locked as of March 2026:
- **MTOW:** 7kg structural ceiling
- **Frame:** Quad, 3D-printed body/hub + 25mm CF tube arms
- **Motor:** Hobbywing X6-SE 380KV (5.5kg max thrust, integrated ESC, CAN protocol)
- **Battery:** 6S, standard RC LiPo
- **Attachment:** Single bottom port, Quiver-compatible

Full ADRs: https://github.com/Arrow-air/project-quiver-mini/tree/main/docs/decisions

---

## What this funds

All bounties are paid in **$ARROW only** at an internal reference price of **$0.30/token**. Quiver Mini is being used as an experiment in $ARROW as a compensation mechanism.

| Bounty | $ARROW | USD equiv | Description |
|--------|--------|-----------|-------------|
| Frame design | 8,000 | $2,400 | CAD for 3D-printed body/hub + 25mm CF tube arm assembly. Deliverables: build123d/STEP files, slicer settings, assembly notes, BOM. Full spec: [docs/bounties/frame-design.md](../bounties/frame-design.md) |
| Mini Main PCB design | 7,000 | $2,100 | Scaled-down Quiver Main PCB for 6S operation. Deliverables: KiCad source, Gerbers, BOM, assembly notes. Footprint to fit frame electronics bay. |
| ArduCopter parameter file + tuning | 2,000 | $600 | Initial parameter file for Quiver Mini (Hobbywing X6-SE, 6S, Pixhawk 6C/6X). Deliverables: .param file, tuning notes, test log. |
| Wiring harness design | 1,500 | $450 | Wire routing and harness spec for v1 build. Deliverables: harness diagram, cut sheet, connector list. |
| Build guide | 1,500 | $450 | First builder documentation. Deliverables: step-by-step assembly guide, sourcing notes, common issues. |
| Test flight validation | 2,500 | $750 | First flight testing and validation report. Deliverables: flight logs, health assessment, sign-off report. |
| **Contingency reserve** | **2,500** | **$750** | Unallocated buffer for scope adjustments, additional small tasks, or bounty revisions. Released at project steward discretion. |
| **Total** | **25,000** | **$7,500** | |

---

## Process

- Bounties are posted individually to #grants-and-bounties as funding is confirmed
- Claims via GitHub issue on [Arrow-air/project-quiver-mini](https://github.com/Arrow-air/project-quiver-mini)
- Review and payment processed per the standard Arrow bounty guide
- Project steward: TBD (thomasg / Vector)

---

## Timeline

| Milestone | Target |
|-----------|--------|
| Snapshot vote passes | TBD |
| Frame design bounty claimed | Within 2 weeks of posting |
| Frame CAD delivered | 4–6 weeks after claim |
| PCB design bounty posted | After frame interior dimensions confirmed |
| First complete build | Q3 2026 |

---

## Success criteria

- At least one complete Quiver Mini v1 build documented and flight-tested
- All deliverables merged into the public repo
- Build guide sufficient for a second builder to replicate without direct support

---

## Notes / open questions

- [ ] Confirm target wallet for fund receipt
- [ ] Confirm project steward (who approves bounty completions and manages contingency)
- [ ] Is $0.30/token the right reference price to use in the proposal, or should we reference market price?
- [ ] Any changes to bounty amounts or scope?
