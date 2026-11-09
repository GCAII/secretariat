# Test Vectors

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Test vectors make conformance reproducible. Each vector is a fixed input, environment assumption, and expected output with a tolerance.

A vector specifies **what to observe**, not what to install. Any mechanism
that performs the observation and reports the same outcome satisfies the
vector.

## Format

One JSON file per vector, named:

```text
<group>/<requirement>-<short-slug>.json
```

Example: `5.1/REQ-5.1.1-no-outbound-requests.json`

`<group>` is the requirement's section (`5.1` … `5.7`), or `schema` for a
vector that tests the report schema rather than a deployment.

## Required fields

| Field | Type | Meaning |
|---|---|---|
| `id` | string | Stable identifier, e.g. `5.1.1-001` |
| `requirement` | string | `REQ-x.y.z`, or `schema` for a schema vector |
| `capabilities` | object | The capability block the vector assumes |
| `description` | string | What outcome the vector observes |
| `input` | object | Prompt, config, or fixture |
| `environment` | object | Properties the environment must have, not a product list |
| `expected` | object | Observed outcome, unit, and tolerance |
| `notes` | string | Known limits |

## Rules

- No personal data, secrets, or proprietary model weights.
- Inputs must be small enough to run on a constrained device.
- Expected output must be deterministic or declare a tolerance.
- A vector that cannot be reproduced is not a vector; it is an anecdote.
- A negative vector states the outcome that MUST NOT occur, and the
  observed rejection when one is expected.

## Status

No deployment vectors yet. Add the first set for:

- [ ] `REQ-5.1.1` no outbound requests in default mode
- [ ] `REQ-5.2.4` resident-set measurement
- [ ] `REQ-5.2.5` temporary-artifact cleanup
- [ ] `REQ-5.4.1` hardware manifest completeness
- [ ] `REQ-5.6.1` authenticated envelope round-trip and tamper rejection

One schema vector exists to prove rejection, and one to prove acceptance:

| Vector | Expects |
|---|---|
| [`schema/not-applicable-without-capability.json`](schema/not-applicable-without-capability.json) | the report schema to **reject** a `not_applicable` result that names no capability |
| [`schema/full-report-l1.json`](schema/full-report-l1.json) | the report schema to **accept** a complete 28-result L1 report |

A validator that has never been shown to reject a bad report is a hope, not
a check. A validator that has never been shown to accept a good one is
untested. Every change to the schema is tested by re-running both vectors.
