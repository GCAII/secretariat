# Deployment Baseline Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.1.*, REQ-5.2.*, REQ-5.3.*; replaces the OSF wiki page `wiki/compliance`.
> **Directives:** none. This policy is procedural and carries no `P-*` identifiers; its obligations are the specification requirements listed above.

## 1. Purpose

Provide a technical baseline for deploying sub-billion-parameter models and edge infrastructure with zero runtime telemetry, privacy-preserving preprocessing, and reproducible evidence.

## 2. Scope

This is a reference architecture, not a legal compliance program. It does not certify compliance with any statute.

## 3. Jurisdictional adaptability

- Adopters map local privacy and data-protection requirements onto the baseline themselves.
- Local amendments are permitted only where they do not reduce a CORE requirement.
- GCAII does not provide legal advice.

## 4. Privacy-preserving inference

- Where the deployment processes personal data, suppression before model
  ingestion is required, per `REQ-5.3.1`.
- Detection methods have category-specific failure modes. Structured
  identifiers and contextual identifiers are reported separately.
- Suppression is never a guarantee of anonymisation.
- See [`pii.md`](pii.md).

## 5. Runtime telemetry

- In the default configuration as defined in the specification, no
  third-party analytics, telemetry hook, or external logging endpoint
  receives data.
- Benchmark results published to a public registry are voluntary and separate from runtime logging.
- See [`telemetry.md`](telemetry.md).

## 6. Memory isolation

- Prompt buffers and intermediate activations reside in storage that does
  not survive power loss.
- Prompt-derived data does not reach a paging store, and no crash artifact
  contains it in readable form.
- Where the platform cannot provide these, the substitute and the residual
  exposure are stated in the report.
- See [`memory-isolation.md`](memory-isolation.md).

## 7. Reproducibility

- Verification depends on evidence, not assertion.
- An anomaly report includes a reproduction and an inspectable trace, and
  states whether remediation exists.
- Every measured quantity carries a unit, a tolerance, and a method.

## 8. Federated participation

- Nodes remain operationally independent.
- Results contributed to the public record are voluntary and licensed for reuse.
- A node's local amendments do not bind another node.
- See [`../agreements/alliances.md`](../agreements/alliances.md).

## 9. Versioning

A local fork states the upstream version it derives from. Security updates
flow from the upstream baseline; a fork that diverges says so. These rules
are defined in [Section 7 of `versioning.md`](../specs/GCAII-STD-0001/versioning.md#section-7).

## 10. Legal note

This policy is technical guidance. It is not legal advice and does not create a compliance obligation. See [`DISCLAIMER.md`](../DISCLAIMER.md).
