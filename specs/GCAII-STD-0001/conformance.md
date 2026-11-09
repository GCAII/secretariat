# Conformance

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Conformance is evidence about a tested configuration. It is not a certificate, an accreditation, or a guarantee.

<a id="section-1"></a>

## 1. Levels

| Level | Name | Who runs it | Evidence | Public |
|---|---|---|---|---|
| **L1** | Declared | Adopter | Published scope declaration | Yes |
| **L2** | Harness-verified | Adopter | Signed JSON report + environment manifest + harness commit | Yes |
| **L3** | Independently reviewed | Second party | Signed attestation + report | Yes |
| **L4** | Continuous | Adopter + auditor | L2/L3 re-run per release | Yes |

L1 requires no harness and no evidence review, but it does require a
published declaration: the specification version, the capability block, the
result for every requirement, and a date. An L1 claim that is not published
is not an L1 claim.

Levels describe the state of the evidence, not the quality of the
implementation. L2 is not a higher grade than L1; it is the same claim with
more evidence published.

<a id="section-2"></a>

## 2. Evidence requirements

A valid L2 report includes:

- `spec_version`, `capabilities`, `conformance_level`, and the `harness`
  version and commit hash;
- hardware manifest (Annex A);
- model hash and inference parameters;
- one result per requirement, with `pass`, `fail`, or `not_applicable`;
  `not_applicable` requires the capability declaration and the evidence
  that the capability is absent (specification 4.8);
- SHA-256 of the report (the canonical report digest; model digests remain
  algorithm-agnostic under REQ-5.7.1);
- a signature or a published hash in the registry.

A valid L3 report adds:

- auditor identity, an independence statement, and the criteria in 2.1 it
  satisfies;
- a second environment run;
- a statement of limitations.

<a id="section-2.1"></a>

### 2.1 Independence criteria

An auditor is independent when none of the following holds: employed by,
contracted to, or financially interested in the submitting party; an author
of the implementation; the person who filed the report; a party to the
report's procurement. The statement is self-declared; verifying the
declaration is outside the scope of this document.

<a id="section-3"></a>

## 3. Review

1. Adopter opens a conformance submission issue.
2. A maintainer checks the schema and the hash.
3. An auditor examines the evidence for L3.
4. The result is recorded in `documents/registry.yaml`.
5. The adopter may publish the report with the result.

Review is best effort with no service level. A report is not recorded until
the schema and hash validate. That check is automated where a validator
exists; otherwise a maintainer runs the same check by hand.

<a id="section-4"></a>

## 4. Expiry and revocation

- L2 reports are valid for 12 months or until the next specification release, whichever is sooner.
- L4 reports expire after 6 months without a re-run.
- A report is revoked if the evidence is invalid, the implementation changes materially, or a security advisory affects the tested configuration.
- Revocation is recorded publicly with a reason.
- If a published `scope_url` stops resolving, the entry is marked `unresolved`. It is not deleted: the record still shows what was claimed and when.
- An expired or superseded entry remains in the registry, marked as such.
  Removing it would erase the record; the archive keeps what was claimed.

<a id="section-5"></a>

## 5. Badge usage

Do not use a badge until this program has a published badge policy and a verified report. Until then, use the phrase:

> declared against GCAII-STD-0001 vX.Y.Z (L1, scope published at <URL>)

and link to the evidence.

<a id="section-6"></a>

## 6. Fees

There are no fees. Conformance is technical, not membership-based.

<a id="section-7"></a>

## 7. Appeals

See [`../../programs/appeals.md`](../../programs/appeals.md).

<a id="section-8"></a>

## 8. Limitations

- A report covers one configuration.
- It does not certify legal compliance.
- It does not guarantee security.
- It does not test every model or hardware combination.
