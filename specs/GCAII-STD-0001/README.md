# GCAII-STD-0001

**Baseline requirements for constrained, zero-telemetry edge inference.**

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Normative:** This specification uses RFC 2119 and RFC 8174 keywords.

## Contents

| File | Purpose |
|---|---|
| [`spec.md`](spec.md) | Normative requirements |
| [`conformance.md`](conformance.md) | Conformance levels, evidence, and reporting |
| [`versioning.md`](versioning.md) | What triggers a patch, minor, or major version |
| [`traceability.md`](traceability.md) | Requirement → policy → capability → vector map |
| [`schemas/`](schemas/) | JSON Schema for machine-readable reports |
| [`test-vectors/`](test-vectors/) | Fixed inputs and expected outputs |
| [`errata/`](errata/) | Corrections to released versions |
| [`changelog.md`](changelog.md) | Version history |
| [`VERSION`](VERSION) | Current version string |

## Scope in one paragraph

This standard defines the minimum technical requirements for deploying sub-billion-parameter language models on resource-constrained hardware with no runtime telemetry, bounded volatile-memory use, and reproducible evidence. It covers inference runtimes, local proxies, and packaging. It does not cover model training, frontier-scale systems, or legal compliance.

## Normative language

- **MUST / MUST NOT** — absolute requirement.
- **SHOULD / SHOULD NOT** — recommended; a deviation requires a recorded reason.
- **MAY** — optional.

Requirements are identified as `REQ-<section>.<subsection>.<n>` — for example `REQ-5.1.1` — so a conformance report can cite them.

## Capabilities

There is no profile system. Every requirement is either CORE — applying to
every implementation and not excludable — or CONDITIONAL, applying only
when the deployment declares the capability true.

| Capability | Declared true when |
|---|---|
| `persists_prompt_data` | prompt or activation data can reach persistent storage, swap, or a crash artifact |
| `persists_index` | any embedding, vector, entity, or n-gram index survives process exit |
| `processes_personal_data` | model input may contain data relating to an identifiable person |
| `stores_data_at_rest` | any prompt-derived data is written to storage |
| `declares_network_channel` | a non-default configuration permits outbound traffic |
| `supports_deterministic_mode` | the runtime offers a reproducible execution mode |

Every report declares all six. A requirement whose capability is false is
reported as `not_applicable`, with evidence that the capability is absent.
See [`spec.md`](spec.md) [Section 4.7](spec.md#section-4.7) and [Section 4.8](spec.md#section-4.8).

## How to cite

> Global Constrained AI Initiative (2026). *GCAII-STD-0001: Baseline requirements for constrained, zero-telemetry edge inference* (v1.0.0). <https://github.com/GCAII/secretariat>

Once a DOI is minted, replace the URL with the DOI in [`documents/registry.yaml`](../../documents/registry.yaml).
