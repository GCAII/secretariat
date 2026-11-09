# Global Constrained AI Initiative

**Secretariat** — the canonical, durable registry for the GCAII Standards series, its conformance records, and the governance that binds them.

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08  
> **Institutional status:** An unincorporated research and conformance initiative. Independence is intentional: no commercial ownership, no certification authority, and no legal personality. Nothing in this repository is legal advice, a certification, or a statement of institutional authority.

## Mandate

The Secretariat publishes, numbers, and records. It does not approve, certify, or enforce. Its role is editorial and procedural: it maintains the canonical text, assigns stable identifiers, and preserves an append-only record of what was published and what was declared.

`GCAII-STD-0001` defines the normative conformance boundary. Implementation runtimes, local security harnesses, and compute nodes operate within that boundary and produce evidence. The standard does not endorse an implementation, and an implementation does not speak for the standard.

## Repository scope

This is the canonical source for:

- The `GCAII-STD-0001` normative specification, JSON Schema, test vectors, errata, and traceability matrix.
- The charter, governance, decision records, and conformance program.
- Policy guidance that elaborates — but never extends — the specification.
- Templates for contribution, institutional liaison, and alliance coordination; issue forms for proposals and disputes.
- The append-only release registry and immutable publication metadata.

Research artifacts (papers, notebooks, datasets) are published through Zenodo and OSF and referenced from [`documents/registry.yaml`](documents/registry.yaml); they are not duplicated here.

## Boundaries

- Not a legal entity, charity, company, or certifying authority.
- Not affiliated with, endorsed by, or endorsing any commercial AI infrastructure provider.
- Not a vendor, product, or implementation repository.
- Not a substitute for jurisdiction-specific legal or compliance advice.
- Not a guarantee of security, fitness, or regulatory conformity.

## Corpus navigation

| Subsystem / artifact | Purpose | Primary entry point |
|---|---|---|
| **Governing instrument** | Scope, authority, and institutional boundaries | [`CHARTER.md`](CHARTER.md) |
| **Governance and process** | Roles, RFC workflow, decisions, and appeals | [`GOVERNANCE.md`](GOVERNANCE.md) |
| **Contribution** | Proposal and pull-request process | [`CONTRIBUTING.md`](CONTRIBUTING.md) |
| **Normative standard** | Requirements, test vectors, errata, and traceability | [`specs/GCAII-STD-0001/README.md`](specs/GCAII-STD-0001/README.md) |
| **Conformance schema** | Machine-readable validation for conformance reports | [`conformance-report.schema.json`](specs/GCAII-STD-0001/schemas/conformance-report.schema.json) |
| **Conformance framework** | Evidence tiers, submission, review, audit, and appeals | [`programs/conformance.md`](programs/conformance.md) |
| **Policy guidance** | Elaboration of the specification boundary; never an extension of it | [`policies/README.md`](policies/README.md) |
| **Security disclosure** | Vulnerability reporting and coordinated disclosure | [`SECURITY.md`](SECURITY.md) |
| **Append-only registry** | Release records, SHA-256 digests, and DOI metadata once assigned | [`documents/registry.yaml`](documents/registry.yaml) |
| **Administrative index** | Non-normative milestones and deferred tracks | [`MILESTONES.md`](MILESTONES.md) |
| **Corpus map** | Non-normative index of every file and directory | [`INDEX.md`](INDEX.md) |

## Versioning and provenance

- Documents carry a status (`draft`, `active`, `superseded`) and a semantic version.
- Released specifications are **immutable**: corrections are published as errata or a new version, never by editing the released text.
- The registry is **append-only**: entries are marked, never deleted.
- Each release is registered in `documents/registry.yaml` with its SHA-256 once the release bundle exists; a DOI is added when one is assigned.
- Superseded material moves to `archive/`, never deletion.

## License

At the 1.0.0 baseline, everything in this repository — including the JSON Schema and test vectors — is licensed **CC BY 4.0**. See [`LICENSE`](LICENSE) for the canonical text.

When executable code and harnesses land, they will be licensed **Apache-2.0**, and the vectors and schemas will move to **CC0 1.0**. The intended split is recorded in [`LICENSING.md`](LICENSING.md); nothing is currently licensed under those terms.

## Contact

- Issues and proposals: GitHub Issues
- Security: see [`SECURITY.md`](SECURITY.md)
- General: `gcaii.secretariat@outlook.com`
