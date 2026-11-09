# Verification Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** `REQ-5.4.*` and `REQ-5.5.*`; replaces the OSF wiki page `wiki/verification`.
> **Directives:** none. This policy is procedural and carries no `P-*` identifiers; its obligations are the specification requirements listed above.

<a id="section-1"></a>

## 1. Purpose

Define how a deployment reports constrained-hardware behaviour so an anomaly
can be reproduced and an absent remediation is stated rather than hidden.

<a id="section-2"></a>

## 2. Scope

Applies to independent research nodes, edge operators, and adopters producing verification evidence. It does not define model quality or legal compliance.

<a id="section-3"></a>

## 3. Collaborative onboarding

- **Calibration window.** A deployment may report a bounded calibration
  period during which it establishes its own baseline. The period and the
  baseline method are stated in the report; results produced inside it are
  marked as such.
- **Remediation over rejection.** A discrepancy is treated as an engineering problem first. The node publishes the trace; a maintainer or reviewer looks for a cause before declaring a failure.
- **No gatekeeping by affiliation.** Access to the test vectors and their methods does not depend on institutional membership.

<a id="section-4"></a>

## 4. Negative results

- Failed runs, quantization bottlenecks, and hardware limitation logs are publishable artifacts.
- A negative result is evidence, not a failed application.
- Publish the environment, the expected result, the observed result, and the reproduction.

<a id="section-5"></a>

## 5. Hardware-aware execution bounds

- Verification prefers a deterministic result and reports the observed
  variance where determinism is not achievable.
- Every measured quantity MUST have a stated unit, a stated tolerance, and
  a stated method. A quantity without all three is not evidence. This
  restates specification 6.5.
- Results from distinct hardware configurations are reported per
  configuration and never averaged across them.

<a id="section-6"></a>

## 6. Versioned artifacts

- Results are assigned a persistent identifier through a registrar, and
  the identifier is stated in the report.
- A report cites the specification version, the conformance level, the
  model hash, and the environment; at L2 and above it also cites the
  harness version.
- A result without a reproduction is not a verification.

<a id="section-7"></a>

## 7. Jurisdictional portability

Verification protocols are designed to be usable across jurisdictions without a centralized cloud hook. This is an architectural property, not a legal compliance claim. See [`DISCLAIMER.md`](../DISCLAIMER.md).

<a id="section-8"></a>

## 8. Checklist

- [ ] Requirement IDs cited.
- [ ] Environment manifest included.
- [ ] Tolerance stated.
- [ ] Negative results preserved.
- [ ] Artefact assigned a persistent identifier.
- [ ] No personal data in the trace.

<a id="section-9"></a>

## 9. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 6](../specs/GCAII-STD-0001/spec.md#section-6)
- [`policies/telemetry.md`](telemetry.md)
