# GCAII-STD-0001 v1.0.0 — release record

> **Status:** Published · **Document date:** 2026-11-08 · **Deposited:** 2026-11-09

## Identity

| Field | Value |
|---|---|
| Document | `GCAII-STD-0001` |
| Version | 1.0.0 |
| Title | Baseline requirements for constrained, zero-telemetry edge inference |
| Tag | [`v1.0.0`](https://github.com/GCAII/secretariat/releases/tag/v1.0.0) |
| Commit | `914c972addc2c8595d9b3486b9270941c704bb09` |
| Version DOI | [10.5281/zenodo.24089533](https://doi.org/10.5281/zenodo.24089533) |
| Concept DOI | [10.5281/zenodo.24089532](https://doi.org/10.5281/zenodo.24089532) |
| Archive | `secretariat-v1.0.0.zip`, 97,511 bytes |
| SHA-256 | `3b33cca8cf25312d80ad625a29bf644ceba86ce8541abc594b87c1b011962951` |
| MD5 | `dcd68892b10c8fffafe8ca282cbe2485` |
| Licence | CC BY 4.0 |
| Signature | none; no signing key is published |

## Contents

- `spec.md`: 28 requirements, 19 CORE and 9 conditional, sections 5.1 to 5.7
- `schemas/conformance-report.schema.json`: JSON Schema Draft 2020-12
- two schema test vectors: one acceptance, one rejection
- charter, governance, RFC process, decision records, errata process
- `documents/registry.yaml`: see the note below

## Registry as of the tag

The registry inside the tagged tree records the pre-registry state:
`releases: []` and `declarations: []`, under a comment dated 2026-11-08. The
release entry was added on `main` after the tag, because it carries the SHA-256
of an archive that could not be hashed before the tag existed.

Three commits modified `documents/registry.yaml` between the tag and this entry.
No other file differs. The archive and the registry are therefore not identical
by design, and a reader comparing them should expect exactly this.

## Gates at release

| Gate | Result |
|---|---|
| markdownlint | 0 errors |
| Link check | 0 broken |
| Requirement counts | 28 / 19 CORE / 9 conditional |
| Schema vectors | 2 of 2 as expected |
| YAML and JSON parse | clean |
| CI at tag commit | green |

## What this release does not claim

No independent review was performed. This is a single-author publication. The
Secretariat publishes, numbers, and records; it does not approve, certify, or
enforce. The release is not a certificate and is not evidence of fitness for any
purpose. No conformance declarations are recorded.

## Cite as

> Global Constrained AI Initiative (2026). *GCAII-STD-0001: Baseline requirements
> for constrained, zero-telemetry edge inference* (v1.0.0).
> <https://doi.org/10.5281/zenodo.24089533>

## Archive

The citable copy is the Zenodo file listed above. GitHub archives of the same tag
are convenient but are not guaranteed byte-stable over time; the SHA-256 in this
record describes the deposited bundle.
