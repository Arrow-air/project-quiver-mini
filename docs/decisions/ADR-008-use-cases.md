# ADR-008: Primary Use Case — Sensor Platform

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Intended Use Cases & Payload Taxonomy](https://github.com/Arrow-air/project-quiver-mini/discussions/11)

## Decision

Quiver Mini v1 primary use case: **sensor platform** (cameras, LiDAR, thermal, multispectral). Docking station / auto-charge / battery swap is on the roadmap.

## In Scope (v1)

- RGB cameras (survey, inspection)
- Thermal cameras
- Multispectral sensors (NDVI, vegetation analysis)
- LiDAR
- Other lightweight sensor payloads up to ~1.5–2kg

## Deprioritized (v1)

**Granular dispensing** (brush bullet, seed spreading): too little payload capacity at this size — Thomas. May revisit at higher MTOW or with a payload-optimized variant.

## Roadmap

**Docking station / auto-charge / battery swap:** Thomas explicitly excited about this. Deserves its own design track — not in v1 scope but influences interface design (attachment port location, power connector access).

## Design Implications

- Payload interface: bottom attachment port with power + data (see ADR-004)
- Ground clearance: important for camera payloads; enclosure design should allow adequate clearance for bottom-mounted sensors
- Weight budget: structure + electronics should leave ~1.5–2kg for payloads
