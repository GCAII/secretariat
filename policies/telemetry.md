# Zero-Telemetry Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.1.1 – REQ-5.1.4

## 1. Purpose

Define what "zero telemetry" means in practice, so an adopter can test it rather than assert it.

## 2. Definition

Zero telemetry means that, in the default configuration, an inference deployment does not transmit prompts, completions, embeddings, derived features, usage counters, crash reports, or model identifiers outside its deployment boundary.

It does not mean the deployment is offline. A feature may require network access; if so, it is off by default and documented.

## 3. Requirements

- **tel-P1 (MUST):** In the **default configuration** as defined in
  [`spec.md`](../specs/GCAII-STD-0001/spec.md) (Section 5.1.1), no outbound request
  occurs during a defined test run.
- **tel-P2 (MUST):** Every destination reachable in a non-default
  configuration is listed with its purpose, trigger, data class, and the
  means by which it is disabled. The report MUST NOT require disclosure of
  internal addresses, subnet ranges, or network topology; purpose, trigger,
  and data class are sufficient.
- **tel-P3 (SHOULD):** Outbound attempts are recorded in a local log that
  is not transmitted.
- **tel-P4 (MUST):** No framework component, dependency, or bundled SDK
  transmits analytics, crash data, or version data in the default
  configuration. A component that cannot be disabled is a declared network
  channel.
- **tel-P5 (MUST):** A report states the method used to observe egress and
  the boundary at which observation occurred.

## 4. Verification

The requirement is an observation at the deployment boundary, not the use
of a particular utility.

1. Establish an environment in which every egress attempt is observable
   and preventable. Any mechanism that achieves this is acceptable.
2. Execute a fixed prompt set.
3. Record each attempt: destination, protocol, payload class, trigger.
4. Report zero attempts, or each attempt mapped to a declared channel.

The report states the observation point and the method. Observation of
actual traffic is stronger than a configuration listing; a configuration
listing alone does not satisfy `REQ-5.1.4`.

## 5. Exceptions

- Model retrieval is permitted as a discrete, documented install step
  outside the tested run.
- A licence or entitlement check is a declared network channel. A
  deployment that performs one is not zero-telemetry in that configuration.
- Benchmark publication is voluntary and separate from runtime behaviour.

## 6. Anti-patterns

- "We don't collect data" without an egress test.
- Telemetry hidden in a dependency.
- A crash reporter enabled by the framework's default.
- An update check that sends a machine identifier.

## 7. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 5.1](../specs/GCAII-STD-0001/spec.md#section-5.1)
- [`specs/GCAII-STD-0001/test-vectors/`](../specs/GCAII-STD-0001/test-vectors/README.md)
