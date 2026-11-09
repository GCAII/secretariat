# Traceability

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

One row per requirement, mapping it to the capability that gates it, the
policy that elaborates it, the vector that would test it, and the boundary
observation that constitutes evidence.

This is an informative index. `spec.md` is normative; where this table and
the specification disagree, the specification wins. Requirement class is
defined once in specification 4.4 and is not repeated here: a row with a
gate is CONDITIONAL, and a row without one is CORE.

No deployment vectors are published yet. A name in the **Vector** column is
a target, not an existing file: a requirement without a published vector can
still be reported, but the report must state the method used (specification
6.1).

## Requirements

| Requirement | Gate | Policy | Vector | Evidence observed at |
|---|---|---|---|---|
| `REQ-5.1.1` | — | `telemetry.md` tel-P1, tel-P4 | `5.1/REQ-5.1.1` | egress at the deployment boundary |
| `REQ-5.1.2` | — | `telemetry.md` tel-P2 | `5.1/REQ-5.1.2` | report field + documentation |
| `REQ-5.1.3` | — | `telemetry.md` tel-P3 | — | local log content |
| `REQ-5.1.4` | — | `telemetry.md` tel-P5 | `5.1/REQ-5.1.4` | boundary observation with a stated method |
| `REQ-5.2.1` | — | `memory-isolation.md` mem-P1, mem-P6 | `5.2/REQ-5.2.1` | storage class of buffers and activations |
| `REQ-5.2.2` | `persists_prompt_data` | `memory-isolation.md` mem-P2 | `5.2/REQ-5.2.2` | paging state and paging content |
| `REQ-5.2.3` | `persists_prompt_data` | `memory-isolation.md` mem-P3 | `5.2/REQ-5.2.3` | dump artifacts after an induced abort |
| `REQ-5.2.4` | — | `memory-isolation.md` mem-P5 | `5.2/REQ-5.2.4` | resident memory and peak allocation |
| `REQ-5.2.5` | — | `memory-isolation.md` mem-P4 | `5.2/REQ-5.2.5` | filesystem state after exit |
| `REQ-5.2.6` | — | `memory-isolation.md` mem-P5 | — | allocation fraction of available memory |
| `REQ-5.3.1` | `processes_personal_data` | `pii.md` pii-P1, pii-P6 | `5.3/REQ-5.3.1` | model context before ingestion |
| `REQ-5.3.2` | `processes_personal_data` | `pii.md` pii-P2, pii-P3 | — | report statement and measured rates |
| `REQ-5.3.3` | — | `pii.md` pii-P4 | — | documentation text |
| `REQ-5.3.4` | — | `pii.md` pii-P5 | — | method description |
| `REQ-5.3.5` | `persists_index` | `pii.md` pii-P7 | `5.3/REQ-5.3.5` | index files and their content |
| `REQ-5.4.1` | — | `verification.md` [Section 6](../../policies/verification.md#section-6) | `5.4/REQ-5.4.1` | report completeness |
| `REQ-5.4.2` | — | `verification.md` [Section 5](../../policies/verification.md#section-5) | — | report statement |
| `REQ-5.4.3` | — | `verification.md` [Section 5](../../policies/verification.md#section-5) | — | run-to-run variance |
| `REQ-5.5.1` | — | `verification.md` [Section 4](../../policies/verification.md#section-4) | — | reproduction and trace |
| `REQ-5.5.2` | — | `verification.md` [Section 4](../../policies/verification.md#section-4) | — | report statement |
| `REQ-5.5.3` | — | `SECURITY.md` | — | disclosure record |
| `REQ-5.6.1` | `stores_data_at_rest` | `cryptography.md` crypto-P1, crypto-P3, crypto-P5 | `5.6/REQ-5.6.1` | read behaviour on a tampered envelope |
| `REQ-5.6.2` | `stores_data_at_rest` | `cryptography.md` crypto-P2 | `5.6/REQ-5.6.2` | key material location |
| `REQ-5.6.3` | `stores_data_at_rest` | `cryptography.md` crypto-P4 | `5.6/REQ-5.6.3` | measured derivation cost |
| `REQ-5.6.4` | `stores_data_at_rest` | `cryptography.md` crypto-P6 | — | report statement |
| `REQ-5.7.1` | — | `supply-chain.md` sc-P1, sc-P2, sc-P7 | `5.7/REQ-5.7.1` | dependency resolution record |
| `REQ-5.7.2` | — | `supply-chain.md` sc-P3, sc-P5 | — | published manifest |
| `REQ-5.7.3` | — | `supply-chain.md` sc-P4 | `5.7/REQ-5.7.3` | rebuild in a clean environment |

## Coverage

28 requirements: 19 CORE and 9 CONDITIONAL. 16 have a planned vector target
and none is published yet; the rest are named here so their absence is
visible rather than assumed.

Two capabilities gate no requirement: `declares_network_channel` is
referenced by 5.1.2, and `supports_deterministic_mode` is covered by 5.4.2.
They are declared in every report but do not appear in the Gate column.

## Schema vectors

| Vector | Expects |
|---|---|
| `schema/not-applicable-without-capability.json` | rejection of an unbacked `not_applicable` claim |
| `schema/full-report-l1.json` | acceptance of a complete 28-result L1 report |

## Maintaining this table

Add a row in the same change that adds a requirement, a capability, or a
vector. A requirement that exists in `spec.md` and not here is a defect in
this index. A row that names a vector that does not exist is a defect in
both.
