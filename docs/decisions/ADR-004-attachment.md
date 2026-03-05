# ADR-004: Attachment Interface — Single Bottom Port, Quiver-Compatible

**Status:** Accepted  
**Date:** 2026-03-05  
**Discussion:** [Design Q5: Attachment Interface](https://github.com/Arrow-air/project-quiver-mini/discussions/4)

## Decision

Quiver Mini v1 will have a **single bottom attachment port** using the Quiver-compatible pogo-pin interface (V1 spec).

## Rationale

- Thomas proposed, Julius and Erick confirmed: one port is sufficient for v1 sensor platform use
- Bottom-only keeps integration simple and the frame design clean
- Quiver payload interoperability is maintained
- KBM noted ground clearance implications for large bottom-mounted payloads — acceptable constraint for v1; side/top ports are v2+ scope

## Interface Spec

Uses the Quiver attachment PCB interface (pogo pin, orientation standardized per Feb 2026 callout: notch on top, pin 1 on drone side). Reference: Arrow-air/project-quiver PR #181.
