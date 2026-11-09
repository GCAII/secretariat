# Index

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

A flat map of this repository. Nothing here is normative or part of the change process — it is a reading aid, not a document. The requirements live in `specs/`; the binding rules live in `CHARTER.md` and `GOVERNANCE.md`.

If this page and a document disagree, the document wins.

## Start here

| File | What it is |
|---|---|
| `README.md` | What this repository is, and what it is not |
| `DISCLAIMER.md` | The non-affiliation and no-authority notice |
| `IDENTITY.md` | Canonical surfaces: names, addresses, identifiers |
| `CHARTER.md` | Scope and authority |
| `MILESTONES.md` | What exists, what is planned, what is deferred |

## Governance

| File | What it is |
|---|---|
| `GOVERNANCE.md` | Roles, RFC process, decision process, appeals |
| `MAINTAINERS.md` | Who currently holds which role |
| `CONTRIBUTING.md` | How to propose a change |
| `CODE_OF_CONDUCT.md` | Behaviour and enforcement |
| `SECURITY.md` | Vulnerability disclosure |
| `NAME.md` | What the name is, what it is not, and who this project is not |
| `GLOSSARY.md` | Terms, normative and informative |
| `CITATION.cff` | How to cite this repository |
| `CHANGELOG.md` | Repository-level changes |

## Specification

| Path | What it is |
|---|---|
| `specs/README.md` | How specifications are numbered and versioned |
| `specs/GCAII-STD-0001/spec.md` | The requirements themselves |
| `specs/GCAII-STD-0001/conformance.md` | Conformance levels and evidence |
| `specs/GCAII-STD-0001/versioning.md` | What triggers a patch, minor, or major version |
| `specs/GCAII-STD-0001/traceability.md` | Requirement → policy → capability → vector map |
| `specs/GCAII-STD-0001/schemas/` | JSON Schema for a conformance report |
| `specs/GCAII-STD-0001/test-vectors/` | Fixed inputs and expected results — **2 schema vectors** |
| `specs/GCAII-STD-0001/errata/` | Corrections to released versions — **no entries yet** |
| `specs/GCAII-STD-0001/VERSION` | Current version string |
| `specs/GCAII-STD-0001/changelog.md` | Specification-level changes |

## Policies

Guidance that elaborates the specification. Not independent requirements.

| File | Subject |
|---|---|
| `policies/telemetry.md` | Runtime telemetry isolation |
| `policies/memory-isolation.md` | Volatile memory and buffers |
| `policies/pii.md` | PII handling and evidence |
| `policies/cryptography.md` | Cryptographic storage |
| `policies/supply-chain.md` | Provenance and dependencies |
| `policies/verification.md` | How conformance is checked |
| `policies/deployment.md` | Deployment baseline |

## Programs

| File | What it is |
|---|---|
| `programs/conformance.md` | Submission and review of conformance reports |
| `programs/audit.md` | Independent audit |
| `programs/appeals.md` | Disputing a decision |

## Agreements

Templates, not executed instruments. See `agreements/README.md` for the caveat that nobody can sign on behalf of an unincorporated project.

| File | What it is |
|---|---|
| `agreements/contributor-agreement.md` | Contribution terms |
| `agreements/institutional-liaison.md` | How an institution engages |
| `agreements/alliances.md` | Inter-initiative coordination |
| `agreements/mou-template.md` | Memorandum of understanding — **not executable as written** |

## Decisions and proposals

| Path | What it is |
|---|---|
| `decisions/` | Architecture Decision Records — what was decided and why |
| `rfcs/` | Proposals not yet decided |

## Documents

| Path | What it is |
|---|---|
| `documents/registry.yaml` | Machine-readable list of published artifacts |
| `documents/releases/` | Immutable release snapshots — **no entries yet** |
| `documents/meetings/` | Notes — **no entries yet** |

## Archive and assets

| Path | What it is |
|---|---|
| `archive/` | Superseded material, kept for provenance — **no entries yet** |
| `assets/` | Diagrams and brand files — **no entries yet** |

## Meta

| Path | What it is |
|---|---|
| `.github/CODEOWNERS` | Review ownership |
| `.github/ISSUE_TEMPLATE/` | Issue forms |
| `.github/workflows/ci.yml` | Link check and lint |
| `.markdownlint.json` | Markdown lint rules |
| `.gitattributes` | Line-ending normalisation |
| `.github/dependabot.yml` | Monthly action updates |
| `.editorconfig` | Editor defaults |
| `.gitignore` | Ignored files |
| `LICENSE` | CC BY 4.0, canonical text |
| `LICENSING.md` | How licensing splits once code exists |
| `LICENSES/` | Reserved for canonical licence texts — **no licence texts yet** |

## Not yet written

These are named in the milestones and do not exist. Nothing in this repository should be read as if they do.

| Thing | Status |
|---|---|
| Dedicated website | not built; the organisation profile at `https://github.com/GCAII` is live |
| Conformance harness | no repository, no code |
| Test vectors | 1 acceptance vector and 1 rejection vector; no deployment vectors |
| Independent auditor | none named |
| Published conformance report | none |
| Released version with a DOI | none — 1.0.0 is published without a DOI |

## Placeholder markers

One marker remains:

| Marker | Means |
|---|---|
| `https://gcaii.invalid/…` | a test fixture that must never resolve |

`.invalid` is reserved by RFC 2606 and can never resolve, so a test fixture cannot be mistaken for a live address. To find every outstanding marker:

```text
grep -rn --include=*.md --include=*.json --include=*.cff --include=*.yml "\.invalid"
```
