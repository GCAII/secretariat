# Changelog

All notable changes to GCAII standards and governance are recorded here. Entries begin at the 1.0.0 baseline; the pre-1.0 draft was never released and is not archived.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] — 2026-11-08

### Added

- **Formal baseline launch.** Official release of `GCAII-STD-0001` (v1.0.0), establishing baseline requirements for constrained, zero-telemetry edge inference of sub-billion-parameter language models.
- **Closed capability set.** Defined six independent boolean capabilities (`persists_prompt_data`, `persists_index`, `processes_personal_data`, `stores_data_at_rest`, `declares_network_channel`, `supports_deterministic_mode`) with strict reporting rules.
- **Machine-executable conformance schema.** Published a strict JSON Schema (Draft 2020-12) at `specs/GCAII-STD-0001/schemas/conformance-report.schema.json`, validating 28 required requirement results, capability gates, and L1–L4 evidence tiers.
- **Test vectors.** Added a positive vector (`test-vectors/schema/full-report-l1.json`) and a negative vector (`test-vectors/schema/not-applicable-without-capability.json`).
- **Traceability matrix.** Added `traceability.md`, mapping all 28 requirements to capability gates, policy elaborations, target test vectors, and observable boundary evidence.
- **Versioning policy.** Added `versioning.md`, defining patch, minor, and major semantics for a standard.
- **Environment and hygiene infrastructure.** Standardised repository governance, strict LF normalisation via `.gitattributes`, cross-platform editor defaults (`.editorconfig`), workspace hygiene (`.gitignore`), and Markdown lint rules (`.markdownlint.json`).
- **Open-science licensing.** Added the canonical CC BY 4.0 `LICENSE` and immutable metadata governance in `CITATION.cff` and `documents/registry.yaml`.

### Changed

- Repository documents are Active at version 1.0.0, dated 2026-11-08.
- Conformance is expressed through independent capability declarations rather than the retired profile vocabulary.

### Deprecated

- Nothing yet. Deprecations are recorded from 1.0.0 forward, or when the conformance harness moves to its own public repository.

### Removed

- The pre-1.0 draft changelog entries. The 0.1.0 draft was never released.

### Fixed

- Nothing yet.

### Security

- Nothing yet.
