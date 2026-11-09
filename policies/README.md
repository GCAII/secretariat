# Policies

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Policies elaborate the normative requirements in [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md). They are guidance: where a policy conflicts with the specification, the specification prevails.

| Policy | Elaborates | Status |
|---|---|---|
| [`telemetry.md`](telemetry.md) | REQ-5.1.* | Active |
| [`memory-isolation.md`](memory-isolation.md) | REQ-5.2.* | Active |
| [`pii.md`](pii.md) | REQ-5.3.* | Active |
| [`verification.md`](verification.md) | REQ-5.4.*, REQ-5.5.* | Active |
| [`cryptography.md`](cryptography.md) | REQ-5.6.* | Active |
| [`supply-chain.md`](supply-chain.md) | REQ-5.7.* | Active |
| [`deployment.md`](deployment.md) | Cross-cutting deployment baseline | Active |

## Directive identifiers

Policies carry numbered directives so a conformance report or a dispute can cite them. Each policy namespaces its own, because a bare `P-1` is ambiguous across seven files.

| Policy | Prefix | Example |
|---|---|---|
| `telemetry.md` | `tel-` | `tel-P1` |
| `memory-isolation.md` | `mem-` | `mem-P1` |
| `pii.md` | `pii-` | `pii-P1` |
| `cryptography.md` | `crypto-` | `crypto-P1` |
| `supply-chain.md` | `sc-` | `sc-P1` |
| `verification.md` | — | procedural, no directives |
| `deployment.md` | — | procedural, no directives |

A policy may state MUST only where it **restates** a requirement already in the specification. A policy may not introduce a new MUST. If something must be mandatory and the spec does not already say it, the spec is wrong and should be amended first.

## Writing rules

- State the requirement ID you are elaborating.
- Separate **requirement** from **rationale** and **verification**.
- Restate a spec MUST if the operational detail needs it; never invent one.
- Record platform differences in an informative section, never in a requirement.
- Add a test vector reference where one exists.
