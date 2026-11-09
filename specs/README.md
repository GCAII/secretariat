# Specifications

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

GCAII publishes versioned specifications under the `GCAII-STD-*` namespace. This page is the catalogue and the numbering policy.

## Catalogue

| ID | Title | Status | Version | Capabilities | DOI |
|---|---|---|---|---|---|
| [`GCAII-STD-0001`](GCAII-STD-0001/README.md) | Baseline requirements for constrained, zero-telemetry edge inference | Active | 1.0.0 | 6, closed set | — |

## Numbering policy

- IDs use four digits: `GCAII-STD-0001`, `GCAII-STD-0002`, …
- An ID is allocated once and never reused, even if the document is withdrawn.
- An ID is stable for the life of the document. The version changes; the ID does not.
- A withdrawn document keeps its ID and is marked `withdrawn`.
- A capability is a boolean declared in the report, not a document suffix and not a new ID.
- Version semantics are defined in [`GCAII-STD-0001/versioning.md`](GCAII-STD-0001/versioning.md).
- An erratum is `GCAII-STD-0001-ERR-001`, not a new ID.
- A major revision is `v2.0.0` of the same ID, not a new number.
- A new document that depends on an existing one gets the next number and cites the dependency.

## Naming rules

- Use a hyphen, not a slash: `GCAII-STD-0001`.
- Always include the full ID in a citation; "GCAII" alone is the organization, not a standard.
- Titles are descriptive; the ID is the stable reference.

## Adding a specification

1. Allocate the next free number.
2. Create `GCAII-STD-NNNN/` with `README.md`, `spec.md`, `conformance.md`, `versioning.md`, `traceability.md`, `changelog.md`, `VERSION`, `schemas/`, `test-vectors/`, and `errata/`.
3. Add the row to the catalogue.
4. Open an RFC with a 14-day comment period.
5. On ratification, publish a release and record the DOI in [`documents/registry.yaml`](../documents/registry.yaml); if the deposit is pending, record the pre-registry state.
