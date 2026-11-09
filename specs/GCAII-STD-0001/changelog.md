# Changelog — GCAII-STD-0001

All notable changes to this specification are recorded here. Entries begin at the 1.0.0 baseline; the pre-1.0 draft was never released and is not archived.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html), as elaborated in [`versioning.md`](versioning.md).

## [1.0.0] — 2026-11-08

### Added

- Initial release: baseline requirements for constrained, zero-telemetry edge inference of sub-billion-parameter language models.
- Closed set of six independent boolean capabilities, declared in every report, with `not_applicable` requiring evidence of absence.
- 28 requirements — 19 CORE and 9 CONDITIONAL — across telemetry isolation, memory isolation, personal-data handling, deterministic reporting, audit trail, cryptographic storage, and supply chain.
- Conformance levels L1–L4, a JSON Schema for machine-readable reports, positive and negative test vectors, and a traceability matrix.
- Versioning policy and errata process.

### Notes

- Requirement IDs are stable within a major version.
- A `MUST` may be downgraded only in a major release.
- A conformance report is valid only for the specification version it names.
