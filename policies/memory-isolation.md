# Memory Isolation Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.2.1 – REQ-5.2.6

## 1. Purpose

Reduce residual prompt and activation data on disk, in swap, and in crash artifacts on constrained hardware.

## 2. Requirements

- **mem-P1 (MUST):** Prompt buffers and intermediate activations reside in
  storage that does not survive power loss. A platform that cannot provide
  such storage is identified in the report per `REQ-5.2.1`, and that
  requirement is reported `fail`.
- **mem-P2 (MUST if `persists_prompt_data`):** Prompt-derived data does not
  reach a paging store in readable form.
- **mem-P3 (MUST if `persists_prompt_data`):** A crash or abort does not
  produce a readable artifact containing prompt or activation data.
- **mem-P4 (MUST):** Temporary artifacts containing prompt or model data
  do not remain after exit. Persistence that cannot be avoided is named in
  the report with its artifact path, data class, and retention period, and
  the requirement is reported `fail`.
- **mem-P5 (MUST):** The report states measured resident memory, peak
  allocation, the measurement method, and peak allocation as a fraction of
  available memory with the reserve left for other functions.
- **mem-P6 (MUST):** Where a required property cannot be provided by the
  platform, the report names the property, the substitute, the residual
  exposure, and the reason. This restates `REQ-5.2.1`.

## 3. Platform examples (informative)

These are known-good mechanisms. They are examples, not requirements; any
mechanism achieving the same outcome satisfies section 2.

| Outcome | Example mechanism |
|---|---|
| Non-persistent storage | memory-backed filesystem, anonymous mapping |
| No readable paging | paging disabled for the process, or encrypted paging |
| No readable crash artifact | dump handling disabled for the process, or encrypted dump |

## 4. Verification

- Observe resident memory and peak allocation by any method that reports
  the process's resident pages, and state which method was used.
- Execute a fixed prompt set and record both figures.
- Observe whether any artifact remains after exit.
- Observe the effective dump policy for the process.
- Observe the paging state of the device.

## 5. Limits

Memory isolation reduces persistence; it does not prevent a privileged attacker from reading process memory. It is not a substitute for full-disk encryption or access control.

## 6. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 5.2](../specs/GCAII-STD-0001/spec.md#section-5.2)
- [`policies/telemetry.md`](telemetry.md)
