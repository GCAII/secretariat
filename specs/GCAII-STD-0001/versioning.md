# Versioning

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

A released specification is immutable. A version is a statement about the
**text**, not about how many implementations exist. This document defines
what each kind of change costs.

<a id="section-1"></a>

## 1. The three levels

| Change | Version | Requires |
|---|---|---|
| Editorial only — a typo, a broken link, a clarification that changes no requirement's meaning | **patch** `1.0.x` | an errata entry; no new report |
| Additive — a new requirement, a new capability, a new optional schema field, a new annex | **minor** `1.x.0` | an RFC; existing reports stay valid for the version they named |
| Invalidating — removing or rewording a requirement so its meaning changes, removing a capability, changing a MUST's scope, adding a required schema field | **major** `x.0.0` | an RFC, a migration note, and an errata entry for the superseded text |

<a id="section-2"></a>

## 2. Rules that hold inside a major version

- A requirement ID never changes. `REQ-5.1.1` means the same requirement in
  `1.0.0` and `1.4.2`.
- A `MUST` is never downgraded. Only a major version may lower a bound.
- A capability is never removed. Only a major version may close the set.
- A required schema field is only added in a major version.
- A new requirement is added at a new number; existing numbers are not
  reused or renumbered.

<a id="section-3"></a>

## 3. What is not a version

| Not a version | Because |
|---|---|
| fixing a broken URL | the link is not normative text |
| correcting a typo | errata, not a release |
| updating an informative example | the example is not a requirement |
| changing the repository layout | the identifiers travel; paths are convenience |
| adding a file that is not part of the specification | repository change, not a standard change |

<a id="section-4"></a>

## 4. Scheme version

The conformance report schema carries `report_version`. It changes only when
a required field changes — which, by section 2, is a major specification
version. A schema change that only adds an optional field leaves
`report_version` unchanged.

<a id="section-5"></a>

## 5. Prereleases

A prerelease such as `1.1.0-rc.1` is not a conformance target. A report
names a released version or it names nothing.

<a id="section-6"></a>

## 6. Relation to errata

Every patch and every major version begins with an erratum. See
[`errata/README.md`](errata/README.md). The released text is never edited in
place; a reader of `1.0.0` can always obtain the same bytes.

<a id="section-7"></a>

## 7. Forks

A fork MUST state the upstream version it derives from. Security updates
flow from the upstream baseline; a fork that diverges MUST say so in its own
documentation. A fork is not this standard, and a conformance claim names
the upstream version it was tested against, not the fork.
