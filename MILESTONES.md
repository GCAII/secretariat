# Milestones

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Non-normative administrative index.** This document records intended work. It is not a specification, a binding commitment, or an assertion of legal authority. Timelines are directional targets.

## Non-Normative Administrative Notice

This document outlines the intended engineering trajectory and milestone tracking for the GCAII initiative.

---

## Phase 1: Baseline Architecture (v1.0.0) — Achieved

Status: Complete (2026-11-08).

- [x] Establish core repository structure and immutable metadata (`CITATION.cff`, `documents/registry.yaml`).
- [x] Ratify normative charter, governance framework, security policy, and canonical CC BY 4.0 licensing.
- [x] Publish `GCAII-STD-0001 v1.0.0` defining constrained, zero-telemetry edge inference constraints for sub-billion parameter models.
- [x] Define six independent boolean capability gates and L1–L4 evidence tiers.
- [x] Publish strict JSON Schema (`conformance-report.schema.json`) and foundational test vectors.
- [x] Establish versioning semantics and comprehensive traceability matrix (`traceability.md`).

---

## Phase 2: Publication Surfaces & Distribution

Target horizon: Post-1.0.

- [ ] Deploy static status and disclaimer pages to public web distribution.
- [ ] Compile normative specification into an immutable PDF artifact and assign official DOI.
- [ ] Stand up public communication channels and coordinate community discovery nodes.
- [ ] Register Zenodo community collection and mint release-bundle DOIs.
- [ ] Synchronize and mirror releases to the Open Science Framework (OSF) project <https://osf.io/zhvm7>.

---

## Phase 3: Conformance Harness & Tooling

Target horizon: Q1 2027.

- [ ] Initialize the standalone `GCAII/conformance-harness` repository infrastructure.
- [ ] Release reference CLI execution utility: `gcaii-harness run --capabilities <file> --report <path>`.
- [ ] Implement deterministic environment manifestation and cryptographically signed report formats.
- [ ] Author reference runtime implementations for local edge deployment verification.

---

## Phase 4: Conformance Pilot & Verification

Target horizon: Q2 2027.

- [ ] Open intake for L2 harness-verified conformance reports.
- [ ] Onboard initial independent technical auditors to review execution evidence.
- [ ] Publish the inaugural peer-reviewed conformance report (subject to adopter consent).

---

## Phase 5: Repository & Operational Maturity

Target horizon: Ongoing.

- [ ] Enforce strict branch protection policies and cryptographic commit signing across maintainer nodes.
- [ ] Execute license separation (splitting documentation under CC BY 4.0, harnesses under Apache-2.0, and schemas/vectors under CC0 1.0) upon the arrival of executable codebases.

---

## Deferred Tracks

The following paths are explicitly excluded from the current operational scope:

- Formal legal incorporation or non-profit entity registration.
- Commercial certification marks or proprietary accreditation schemes.
- Paid membership tiers or institutional funding models.
