# Releases

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Immutable snapshots of published documents.

## Contents of a release

- The document as published (PDF and/or rendered HTML).
- A `SHA256SUMS` file.
- A detached signature, if signing is available.
- A `CITATION.cff` or citation block.
- A link to the DOI.

## Naming

```text
<document>-<version>-<date>/
```

Example: `GCAII-STD-0001-1.0.0-2026-11-08/`

## Rules

- Never edit a released file.
- Never delete a release; move superseded material to `archive/`.
- Publish the DOI in `registry.yaml` before announcing a DOI-bearing release;
  record any pre-registry baseline explicitly.
- Verify the signature and hash before mirroring.

## First release checklist

- [ ] Spec version and date are final.
- [ ] Changelog is updated.
- [ ] Schema validates.
- [ ] Test vectors pass.
- [ ] PDF/HTML is generated from the tagged commit.
- [ ] SHA-256 is recorded.
- [ ] Zenodo/OSF DOI is minted, or the release is explicitly recorded as pre-registry.
- [ ] Registry entry is added, or the pre-registry state is recorded.
