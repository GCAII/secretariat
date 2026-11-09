# Governance

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

This document defines how GCAII makes decisions, who may make them, and how a decision can be challenged. It complements [`CHARTER.md`](CHARTER.md).

## 1. Roles

| Role | Responsibility | Authority |
|---|---|---|
| **Maintainer / Editor** | Review and merge changes, publish releases, appoint auditors | Merge and release |
| **Secretariat** | Keep the canonical record: publish versions, assign identifiers, record declarations | Duties, not powers: it does not approve, certify, accredit, or enforce |
| **Auditor** | Run or review conformance evidence | Conformance findings only |
| **Contributor** | Propose changes, file issues, submit test vectors | None beyond contribution |
| **Adopter** | Implement or deploy a GCAII specification | None over the standard |

Roles are listed in [`MAINTAINERS.md`](MAINTAINERS.md). A contributor becomes a maintainer by sustained, reviewed contribution and nomination by an existing maintainer.

## 2. Decision rule

Two kinds of questions are decided differently:

- **Technical questions** (does an implementation meet a requirement?) are settled by reproducible evidence and the conformance harness. They are not decided by vote.
- **Governance questions** (should the requirement exist? what is in scope?) are settled by rough consensus of active maintainers after public comment.

This resolves the tension between "evidence over authority" and "community governance": evidence decides facts, consensus decides scope.

## 3. RFC process

1. Open an issue or draft an RFC from [`rfcs/0000-template.md`](rfcs/0000-template.md).
2. Announce a public comment period of at least 14 days for normative changes.
3. Discuss in the RFC thread; summarize objections in the document.
4. Maintainers seek rough consensus.
5. If consensus is blocked, a fallback vote is held: two-thirds of active maintainers, quorum of half.
6. Record the outcome as an ADR in [`decisions/`](decisions/README.md).
7. Update the changelog and, for a release, the registry.

## 4. Voting fallback

- Eligible voters: active maintainers listed in `MAINTAINERS.md`.
- Quorum: half of eligible voters.
- Threshold: two-thirds of votes cast for normative changes; simple majority for process changes.
- Votes are public and recorded in the ADR.

A vote is a last resort. If a vote is routine, the governance is broken.

## 5. Conflicts of interest

Maintainers must disclose employment, consulting, or financial interests that could affect a decision. A conflicted maintainer may argue but must abstain from the final decision. Disclosures are recorded in the ADR.

## 6. Appeals

Any participant may appeal a conformance or governance decision under [`programs/appeals.md`](programs/appeals.md). Appeals are decided by a panel of maintainers not involved in the original decision.

## 7. Records

- Decisions: `decisions/ADR-*.md`
- Releases: `documents/registry.yaml`
- Meeting notes, if any: `documents/meetings/`
- Public comment: linked from the RFC

Records are public unless they contain a security embargo or personal data.

## 8. Removal and emeritus

A maintainer who is inactive for 12 months may be moved to emeritus by consensus. Removal for cause requires an appealable decision under Section 6 and a recorded ADR.

## 9. Amendments

Changes to this document follow the RFC process. Changes to the Charter follow [`CHARTER.md`](CHARTER.md) Section 8.

## 10. Continuity

The record outlives the role that keeps it. Three commitments make that
true rather than aspirational:

- **Mirror.** The repository is mirrored to a second location. The mirror is
  a copy, not a fork: it is expected to match.
- **The record is the text, not the person.** Any copy of a release whose
  digest matches is canonical. No permission is required to read, quote, or
  archive it.
- **If maintenance stops.** The repository remains the record. No further
  versions are issued, the changelog is closed rather than rewritten, and
  the registry is left as it stands.

Nothing required to read the record is held in a private place. There is no
secret key whose loss would make a published version unreadable.
