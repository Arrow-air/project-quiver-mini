# ADR-002: Enclosure — Purpose-Built Smaller

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q2: Enclosure Size](https://github.com/Arrow-air/project-quiver-mini/discussions/2)

## Decision

Quiver Mini will use a **purpose-built smaller enclosure**, not the full Quiver body dimensions.

## Context

The Quiver enclosure was designed for a 25kg platform. Two approaches were evaluated: reuse the Quiver body (Julius's Kestrel does this), or design a Mini-specific enclosure.

## Rationale

- Kestrel handles the max-reuse approach — the community design should offer something distinct
- A properly-sized enclosure improves proportions, weight, and is more representative of the "Mini" category
- The Quiver **attachment interface** (pogo pin PCB) is still reused for payload compatibility — just the outer enclosure changes
- New CAD is required but well-scoped

## Consequences

- Enclosure CAD is needed before first build — natural first hardware bounty
- Main PCB layout may need minor adjustments for new form factor
- Quiver payload compatibility is preserved via the attachment interface
