# Milestones

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Non-normative administrative index.** This document records intended work. It is not a specification, a binding commitment, or an assertion of legal authority. Timelines are directional targets.

## Non-Normative Administrative Notice

This document outlines the intended engineering trajectory and milestone tracking for the GCAII initiative.

---

## Phase 1: Baseline Architecture (v1.0.0) — Achieved

Status: Complete (2026-11-08).

- [x] Establishment of the core repository structure and immutable metadata (`CITATION.cff`, `documents/registry.yaml`).
- [x] Ratification of the normative charter, governance framework, security policy, and canonical CC BY 4.0 licensing.
- [x] Publication of `GCAII-STD-0001 v1.0.0`, defining baseline requirements for constrained, zero-telemetry edge inference of sub-billion-parameter models.
- [x] Definition of six independent boolean capability gates and the L1–L4 evidence tiers.
- [x] Publication of the strict JSON Schema (`conformance-report.schema.json`) and the foundational test vectors.
- [x] Establishment of versioning semantics and the traceability matrix (`traceability.md`).

---

## Phase 2: Publication Surfaces & Distribution

Target horizon: Post-1.0.

- [ ] Deployment of static status and disclaimer pages to public web distribution.
- [x] Deposition of the 1.0.0 corpus on Zenodo and recording of its version DOI in the registry (2026-11-09).
- [ ] Compilation of the normative specification into an immutable PDF artifact.
- [x] Registration of the Zenodo community collection and minting of the release-bundle DOI (2026-11-09).
- [ ] Establishment of public communication channels and coordination with community discovery nodes.
- [ ] Synchronisation and mirroring of releases to the Open Science Framework project <https://osf.io/zhvm7> (project public; content mirror pending).

---

## Phase 3: Conformance Harness & Tooling

Target horizon: Q1 2027.

- [ ] Initialisation of the standalone `GCAII/conformance-harness` repository.
- [ ] Release of the reference CLI execution utility: `gcaii-harness run --capabilities <file> --report <path>`.
- [ ] Implementation of deterministic environment manifestation and cryptographically signed report formats.
- [ ] Authorship of reference runtime implementations for local edge-deployment verification.

---

## Phase 4: Conformance Pilot & Verification

Target horizon: Q2 2027.

- [ ] Opening of intake for L2 harness-verified conformance reports.
- [ ] Onboarding of the first independent technical auditors for review of execution evidence.
- [ ] Publication of the first independently reviewed conformance report, subject to adopter consent.

---

## Phase 5: Repository & Operational Maturity

Target horizon: Ongoing.

- [ ] Enforcement of strict branch protection and cryptographic commit signing across maintainer nodes.
- [ ] Licence separation on arrival of executable code: documents under CC BY 4.0, harnesses under Apache-2.0, schemas and vectors under CC0 1.0.

---

## Deferred Tracks

The following paths are explicitly excluded from the current operational scope:

- Formal legal incorporation or non-profit entity registration.
- Commercial certification marks or proprietary accreditation schemes.
- Paid membership tiers or institutional funding models.

