# ADR-0002 — GCAII Standards namespace

> **Status:** Accepted · **Version:** 1.0.0 · **Date:** 2026-11-07 · **Supersedes:** none

## Context

Standard identifiers require complete uniqueness across automated schema registries, citation indices, and verification harnesses. Unstandardized or variable-length prefixes create collisions in public registries and cause ambiguity in automated evaluation pipelines.

Establishing a stable, reproducible specification enclave requires locking a precise, collision-free identifier scheme prior to tagging version `1.0.0`.

## Decision

1. The standards series is **GCAII Standards**.
2. All specification documents use the formal prefix **`GCAII-STD-`**. The retired `GCAIS-STD-*` prefix is not used.
3. The baseline document is designated **`GCAII-STD-0001`**.
4. Use four-digit, zero-padded IDs consistently (`0001` series).
5. The ID is stable; the version changes.
6. No separate standards body is created. GCAII is the steward and secretariat.

## Consequences

- The primary specification path is locked to `specs/GCAII-STD-0001/`.
- All references, schema `$id` fields, registry examples, issue templates, and glossary entries are updated to `GCAII-STD-0001`.
- Early pre-release working drafts are fully superseded by `GCAII-STD-0001`; frozen historical provenance records on OSF and Zenodo remain untouched.
- If a distinct series is desired later, it can be introduced without changing the first ID.

## Links

- [`specs/README.md`](../specs/README.md)
- [`GLOSSARY.md`](../GLOSSARY.md)
- [`NAME.md`](../NAME.md)

## Note

**2026-11-08.** This project claims no trademark in the name and no exclusive right to the initials; see [`NAME.md`](../NAME.md). The decision itself — to adopt **`GCAII-STD-0001`** and enforce four-digit zero-padded identifiers — stands unchanged and absolute.
