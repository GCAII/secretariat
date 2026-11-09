# PII Handling Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.3.1 – REQ-5.3.5

## 1. Purpose

Describe filtering of personal data before it reaches model context, and the
treatment of any persisted index, without overstating what either can do.

## 2. Scope

This policy covers data reaching model context and any index derived from
it. It does not cover model output filtering or legal anonymisation.

## 3. Requirements

- **pii-P1 (MUST if `processes_personal_data`):** Personal identifiers of
  the categories the deployment declares do not reach model context
  unsuppressed.
- **pii-P2 (MUST):** The report documents the detection method, the
  categories it targets, and its known failure modes per category.
- **pii-P3 (MUST):** Per-category false-positive and false-negative rates
  are measured on a corpus named in the report. An unmeasured method is not
  a documented method; the requirement is reported `fail`.
- **pii-P4 (MUST NOT):** Documentation MUST NOT claim that suppression
  guarantees anonymisation, non-identifiability, or legal compliance.
- **pii-P5 (SHOULD):** Where the declared categories include contextual
  identifiers, suppression SHOULD combine at least two independent
  methods.
- **pii-P6 (MUST):** Suppressed values do not appear in plaintext in any
  log, trace, or index.
- **pii-P7 (MUST if `persists_index`):** A persisted index is reported as
  personal-data-bearing, per `REQ-5.3.5`.

## 4. Categories

Structured: email, phone, government ID, payment card, IP address, API key, file path with a username.

Contextual: names, addresses, employer, relationships, location, health information.

Method choice is open. Synthetic validation (a checksum or format rule) is
effective for structured identifiers and does not generalise to contextual
ones. Both categories MUST be reported separately.

## 5. Verification

- Publish the detection method and the test corpus.
- Report precision and recall per category.
- Include adversarial examples: obfuscated emails, spaced digits, Unicode homoglyphs.
- Record the version of the detection method.

## 6. Legal note

This policy is technical guidance, not legal advice. Whether a deployment processes personal data, and on what basis, depends on jurisdiction and context. Adopters are responsible for their own assessment.

## 7. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 5.3](../specs/GCAII-STD-0001/spec.md#section-5.3)
- [`policies/telemetry.md`](telemetry.md)
