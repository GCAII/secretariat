# Errata

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Released specifications are immutable. Corrections are published here and in
a new version; the released text is not edited.

Every patch and every major version begins with an entry in this table. A
version without a corresponding erratum is a version nobody can explain.

The `1.0.0` baseline is the exception: it is the initial publication and has
no prior version to correct.

## Types

| Type | Meaning | Version effect |
|---|---|---|
| **editorial** | a typo, a broken link, or wording that changes no requirement's meaning | patch, `1.0.x` |
| **substantive** | a requirement's meaning, scope, or bound changes | minor or major, per [`versioning.md`](../versioning.md) |

The distinction is decided by asking one question: *could a report that
passed under the old text fail under the new text?* If yes, it is
substantive.

## Process

1. File an issue with the requirement ID and the defect.
2. A maintainer records the type — editorial or substantive — in the table
   below, with a reason.
3. An editorial erratum is published as a dated entry and, where a patch
   version is cut, referenced from its changelog entry.
4. A substantive change requires an RFC and a new minor or major version.
5. Every erratum names the affected version and the version that carries the
   fix.
6. An erratum is closed only when the fix is published. Closing an erratum
   without a released fix leaves the defect open by definition.

## Entries

| ID | Version | Requirement | Type | Status | Date | Fixed in |
|---|---|---|---|---|---|---|
| *None* | | | | | | |
