# Supply Chain Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.7.1 – REQ-5.7.3

## 1. Purpose

Make a conformance claim traceable to the exact software and model that was tested.

## 2. Requirements

- **sc-P1 (MUST):** Every dependency is identified by an immutable
  reference and recorded in the report.
- **sc-P2 (MUST):** Model weights are identified by a cryptographic digest
  of at least 256 bits, with the algorithm named.
- **sc-P3 (SHOULD):** A release publishes a digest manifest. Where a signing
  mechanism is available, the release SHOULD also publish a detached
  signature over the manifest; where none is published, the report states
  why.
- **sc-P4 (MUST):** The report states whether the build is reproducible.
  Where it is not, each source of deviation is listed.
- **sc-P5 (SHOULD):** A machine-readable dependency inventory is published
  for code releases. Any format in common use is acceptable.
- **sc-P6 (MUST):** Dependencies are not retrieved during a test run. This
  restates specification 6.4.
- **sc-P7 (MUST NOT):** Conformance MUST NOT require publication of model
  weights or source code. A digest establishes identity without disclosure;
  whether to publish is a separate decision the standard does not make.

## 3. Verification

- Recompute the digest of the artefact as deployed and compare.
- Rebuild from the recorded references in a clean environment.
- Verify the signature over the manifest, if one is published.
- Compare the dependency inventory with the packages actually present.

## 4. Release checklist

- [ ] Release is signed.
- [ ] Digest manifest is published.
- [ ] Registry entry includes a persistent identifier and a digest.
- [ ] Dependency inventory is attached.
- [ ] Changelog is updated.

## 5. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 5.7](../specs/GCAII-STD-0001/spec.md#section-5.7)
- [`SECURITY.md`](../SECURITY.md)
