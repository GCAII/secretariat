# Documents and Releases

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

This directory is the release registry and the home of immutable snapshots.

## Contents

| Path | Purpose |
|---|---|
| [`registry.yaml`](registry.yaml) | Machine-readable index of releases and declarations |
| [`releases/`](releases/README.md) | Signed PDFs, hashes, and archived bundles |
| [`meetings/`](meetings/README.md) | Public meeting notes, if any |

## Two records, not one

The registry holds two lists. They are recorded by the same role and mean
different things.

| List | What it records | Who decides it |
|---|---|---|
| `releases` | a version of a document was published | the Secretariat publishes |
| `declarations` | an adopter filed a conformance claim | the adopter claims; the Secretariat records |

A release is a statement about text. A declaration is a statement about a
tested configuration. Neither implies the other.

## Pre-registry state

The 1.0.0 baseline is a repository publication. Its immutable release bundle
and DOI are pending, so `registry.yaml` has no release entry yet. This is a
recorded state, not a missing record: the entry is added when the bundle
SHA-256 exists. CHARTER 6.2 and 6.2.1 are satisfied when the deposit lands.

## Release entry fields

| Field | Required | Meaning |
|---|---|---|
| `id` | yes | `<document>-<version>-<date>` |
| `document` | yes | `GCAII-STD-0001` |
| `title` | yes | human-readable title of the released document |
| `version` | yes | released version, never a prerelease |
| `date` | yes | publication date, `YYYY-MM-DD` |
| `url` | yes | canonical location of the text |
| `sha256` | yes, once the bundle exists | digest of the archived bundle |
| `archive` | no | persistent identifier, once assigned |
| `notes` | no | what changed |

## Declaration entry fields

| Field | Required | Meaning |
|---|---|---|
| `id` | yes | `DECL-NNNN`, assigned in filing order |
| `publisher` | yes | who filed the claim |
| `subject` | yes | implementation name and version |
| `spec_id` | yes | `GCAII-STD-0001` |
| `spec_version` | yes | the version tested, e.g. `1.0.0`; a claim does not carry forward |
| `level` | yes | `L1`–`L4` |
| `date` | yes | filing date |
| `scope_url` | yes | where the declaration is published |
| `report_url` | at L2+ | the report itself |
| `report_sha256` | at L2+ | digest of the report |
| `capabilities` | yes | all six booleans, named explicitly: `persists_prompt_data`, `persists_index`, `processes_personal_data`, `stores_data_at_rest`, `declares_network_channel`, `supports_deterministic_mode` |
| `status` | yes | `active`, `superseded`, `revoked`, `expired`, or `unresolved` |
| `decision` | at L2+ | `verified`, `verified_with_limitations`, `returned`, or `rejected` |
| `decision_date` | at L2+ | date the review decision was recorded, `YYYY-MM-DD` |
| `reviewer` | at L2+ | who recorded the decision |
| `notes` | no | reason, for a status other than `active` |

## Rules

- A release is identified by `document`, `version`, `date`, `archive`, and `sha256`.
- A declaration is identified by its `report_sha256` where one exists.
- A released file is never edited. Corrections are errata or a new version.
- The registry is append-only. An expired or revoked entry is marked, not deleted.
- The Secretariat cannot change a filed declaration without invalidating its
  hash. That constraint runs against the record-keeper, not the adopter.
- A declaration against an earlier `spec_version` remains a true record of
  what was tested. It is not a claim against the current text.

## Release naming

```text
<document>-<version>-<date>
```

Example: `GCAII-STD-0001-1.0.0-2026-11-08`
