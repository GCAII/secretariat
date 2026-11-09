# ADR-0001 — Record architecture decisions

> **Status:** Accepted · **Date:** 2026-11-03 · **Supersedes:** none

## Context

GCAII publishes standards and governance documents. Decisions about requirements, scope, and process need a durable record that survives turnover and does not depend on chat history.

## Decision

Use Architecture Decision Records (ADRs) in `decisions/`, one file per decision, numbered sequentially.

- Technical decisions are informed by reproducible evidence.
- Governance decisions follow the RFC process and rough consensus.
- An accepted ADR is not edited; it is superseded by a new ADR.
- Each ADR links the RFC and the release it affects.

## Consequences

- Decisions are discoverable and citable.
- The repository grows by addition, not rewriting.
- Contributors must write a short ADR for structural changes; this is deliberate friction.
- The ADR index in `decisions/README.md` must be updated with each new record.

## Links

- [`GOVERNANCE.md`](../GOVERNANCE.md)
- [`rfcs/README.md`](../rfcs/README.md)
