# Conformance Program

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

This document defines the process for submitting and recording a conformance claim. Technical levels and evidence are defined in [`specs/GCAII-STD-0001/conformance.md`](../specs/GCAII-STD-0001/conformance.md).

## 1. Eligibility

Any implementer may submit, including individuals, research groups, and commercial vendors. There is no membership requirement and no fee.

## 2. Submission

1. Declare the capability block (specification [Section 4.7](../specs/GCAII-STD-0001/spec.md#section-4.7)) and choose a level (L1–L4).
2. At L2 and above, run the harness and record its version and commit.
3. Produce a JSON report valid against the schema.
4. Publish the report, or its SHA-256, in a stable location.
5. Open a conformance submission issue with the report link and hash.

## 3. Review

| Step | Who | Time target |
|---|---|---|
| Schema and hash check | Maintainer | 3 days |
| Technical review | Maintainer or auditor | 14 days |
| Independent review (L3+) | Auditor | 30 days |
| Record | Secretariat | 3 days |

Targets are best effort. A volunteer project may take longer, and no
declaration is invalid because a target was missed.

## 4. Decision

Possible outcomes:

- **Verified** — evidence satisfies the declared level.
- **Verified with limitations** — pass, with a published limitation.
- **Returned** — missing or invalid evidence; the submitter may resubmit.
- **Rejected** — evidence is misleading or the implementation does not meet a MUST.

A decision is recorded in [`documents/registry.yaml`](../documents/registry.yaml) with a reason.

## 5. Badge and claims

Until a badge policy is published, use the phrase defined in [`conformance.md`](../specs/GCAII-STD-0001/conformance.md#section-5):

> declared against GCAII-STD-0001 vX.Y.Z (L1, scope published at <URL>)

At L2 and above, keep the same phrasing and add the report link, for example:

> declared against GCAII-STD-0001 vX.Y.Z (L2, scope published at <URL>; report: <URL>)

Do not use the word "certified" or a badge.

## 6. Expiry and revocation

- L2: 12 months or the next specification release.
- L4: 6 months without a re-run.
- Revoked on invalid evidence, material change, or a relevant security advisory.

Revocation is public and appealable.

## 7. Fees and conflicts

GCAII charges no fee. Independent auditors may charge for their own time; a reviewer with a commercial interest in the outcome must recuse. See [`audit.md`](audit.md).

## 8. Records

Every decision is public unless it contains personal data or a security embargo. The registry is append-only.
