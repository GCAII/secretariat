# GCAII-STD-0001 — Specification

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Normative:** RFC 2119 / RFC 8174 keywords apply.

<a id="section-1"></a>

## 1. Scope

This specification defines baseline requirements for constrained, zero-telemetry inference of sub-billion-parameter language models. It applies to inference runtimes, local proxies, and packaging on hardware where memory, compute, or network access is limited.

It does not define model quality, training procedure, or legal compliance.

<a id="section-2"></a>

## 2. Normative references

- RFC 2119 — Key words for use in RFCs to indicate requirement levels.
- RFC 8174 — Ambiguity of uppercase and lowercase in RFC 2119 keywords.
- RFC 3339 — Date and time on the internet.
- JSON Schema 2020-12 — Report validation.

<a id="section-3"></a>

## 3. Terms and definitions

See [`GLOSSARY.md`](../../GLOSSARY.md). Terms used normatively: **deployment boundary**, **runtime telemetry**, **default configuration**, **zero-telemetry**, **volatile memory**, **conformance report**, **harness**, **test vector**, **CORE requirement**, **CONDITIONAL requirement**, **capability**, **not_applicable**, **evidence of absence**. Their definitions in the glossary are part of this specification; where the glossary and a policy disagree, the glossary prevails.

<a id="section-4"></a>

## 4. Conformance

<a id="section-4.1"></a>

4.1 An implementation conforms to this specification at a declared conformance level if it satisfies every applicable requirement — every CORE requirement, and every CONDITIONAL requirement whose capability is true — provides the evidence required by [`conformance.md`](conformance.md), and, where it deviates from a SHOULD, records the reason.

<a id="section-4.2"></a>

4.2 A conformance report MUST state the specification version, every capability in 4.7, the conformance level, the environment, and the result for each requirement. A report at L1 MUST include an `assessment` object naming the date and the URL at which its scope was published. A report at L2 or above MUST include the harness name, version, and commit.

<a id="section-4.3"></a>

4.3 A report MUST NOT state a result for a requirement it did not test.

<a id="section-4.4"></a>

4.4 A requirement with no capability gate is **CORE**: it applies to every implementation and MUST NOT be excluded by an adopter. A requirement with a capability gate is **CONDITIONAL**: it applies only when its declared capability is true. Every requirement has exactly one class:

| Class | Requirements | Gate |
|---|---|---|
| CORE | 5.1.1, 5.1.2, 5.1.3, 5.1.4, 5.2.1, 5.2.4, 5.2.5, 5.2.6, 5.3.3, 5.3.4, 5.4.1, 5.4.2, 5.4.3, 5.5.1, 5.5.2, 5.5.3, 5.7.1, 5.7.2, 5.7.3 | — |
| CONDITIONAL | 5.2.2, 5.2.3 | `persists_prompt_data` |
| CONDITIONAL | 5.3.1, 5.3.2 | `processes_personal_data` |
| CONDITIONAL | 5.3.5 | `persists_index` |
| CONDITIONAL | 5.6.1, 5.6.2, 5.6.3, 5.6.4 | `stores_data_at_rest` |

The four requirements that define this standard's minimum scope are `5.1.1`, `5.1.2`, `5.1.4`, and `5.2.1`. A report that does not evidence all four is not a report against this standard at any level.

<a id="section-4.5"></a>

4.5 A CONDITIONAL requirement applies only when its declared capability (4.7) is true. The capability set is closed at this version: a new capability requires a minor version, and a report declaring a capability not listed in 4.7 is invalid.

<a id="section-4.6"></a>

4.6 A conformance report MUST declare every capability. A requirement whose capability is false MUST be reported as `not_applicable`, with the evidence that the capability is absent. `not_applicable` is not a pass, a fail, or a skip.

A capability declaration MUST accurately describe the tested configuration. A declaration contradicted by the evidence is a false declaration, and the report is invalid.

<a id="section-4.7"></a>

4.7 Capabilities, each boolean:

| Capability | True when | Gates |
|---|---|---|
| `persists_prompt_data` | prompt or activation data can reach persistent storage, swap, or a crash artifact | 5.2.2, 5.2.3 |
| `persists_index` | any embedding, vector, entity, or n-gram index survives process exit | 5.3.5 |
| `processes_personal_data` | model input may contain data relating to an identifiable person | 5.3.1, 5.3.2 |
| `stores_data_at_rest` | any prompt-derived data is written to storage | 5.6.1, 5.6.2, 5.6.3, 5.6.4 |
| `declares_network_channel` | a non-default configuration permits outbound traffic | — (referenced by 5.1.2; gates nothing) |
| `supports_deterministic_mode` | the runtime offers a reproducible execution mode | — (gates nothing; 5.4.2 covers both branches) |

<a id="section-4.8"></a>

4.8 Evidence of absence is an inspectable artifact: a file listing, a directory listing, a configuration excerpt, or an observed process or device state. A bare assertion is not evidence. The form is adopter-chosen; the artifact MUST be reproducible by a reviewer.

<a id="section-4.9"></a>

4.9 A conformance report is valid only for the specification version it names. A new version does not carry an existing claim forward; a claim against an earlier version remains a true record of what was tested, not a claim against the current text.

<a id="section-5"></a>

## 5. Requirements

<a id="section-5.1"></a>

### 5.1 Runtime telemetry isolation

- **REQ-5.1.1 (CORE, MUST):** In the **default configuration** — a fresh
  install with no configuration change, no opt-in, and no account linkage
  — an implementation MUST NOT transmit runtime telemetry, prompts,
  completions, embeddings, derived features, or model identifiers outside
  the deployment boundary.
- **REQ-5.1.2 (CORE, MUST):** Every non-default configuration that
  permits outbound traffic MUST be (a) opt-in, (b) documented with its
  destination, purpose, trigger, and data class, (c) reversible without
  data loss, and (d) declared in the conformance report as
  `declares_network_channel = true`.
- **REQ-5.1.3 (SHOULD):** An implementation SHOULD record outbound
  connection attempts in a local log that is not itself transmitted.
- **REQ-5.1.4 (CORE, MUST):** A conformance report MUST include evidence,
  obtained by observing network behaviour at the deployment boundary, that
  the default configuration makes no outbound request during a defined and
  documented test run.

<a id="section-5.2"></a>

### 5.2 Memory isolation

- **REQ-5.2.1 (CORE, MUST):** Prompt buffers and intermediate activations
  MUST reside in storage that does not survive power loss. If a component
  cannot meet this, the report MUST name the component, the storage used
  instead, the residual exposure, and the reason, and the result for this
  requirement MUST be `fail`.
- **REQ-5.2.2 (MUST if `persists_prompt_data`):** Data that could reach a
  swap device or equivalent paging store MUST either be prevented from
  doing so or written only in a form unreadable without key material held
  outside that store.
- **REQ-5.2.3 (MUST if `persists_prompt_data`):** A crash, abort, or
  signal MUST NOT produce an artifact containing prompt or activation data
  in readable form.
- **REQ-5.2.4 (MUST):** A report MUST state measured resident memory and
  peak allocation, and MUST name the measurement method.
- **REQ-5.2.5 (MUST):** Temporary artifacts containing prompt or model
  data MUST NOT remain after exit. Where persistence is unavoidable, the
  report MUST name the artifact, the data class it contains, and its
  retention period, and the result for this requirement MUST be `fail`.
- **REQ-5.2.6 (MUST):** The report MUST state peak allocation as a fraction
  of available memory and the reserve left for other functions.

<a id="section-5.3"></a>

### 5.3 Personal-data handling

- **REQ-5.3.1 (MUST if `processes_personal_data`):** Data reaching model
  context MUST NOT contain unsuppressed personal identifiers of the
  categories the deployment documents. Suppressed values MUST NOT appear in
  plaintext in any log, trace, or index.
- **REQ-5.3.2 (MUST if `processes_personal_data`):** Filtering MUST be
  documented with its categories, false-positive behavior, and known
  limits. Per-category false-positive and false-negative rates MUST be
  measured on a corpus named in the report.
- **REQ-5.3.3 (MUST NOT):** A conformance report MUST NOT claim that filtering guarantees anonymization or legal compliance.
- **REQ-5.3.4 (SHOULD):** Where the declared categories include
  contextual identifiers, suppression SHOULD combine at least two
  independent detection methods.
- **REQ-5.3.5 (MUST if `persists_index`):** Any persisted embedding,
  vector, entity, or n-gram index MUST be treated as personal-data-bearing.
  The report MUST state the index type, whether it persists, and what a
  stored entry can reveal.

<a id="section-5.4"></a>

### 5.4 Deterministic execution and reporting

- **REQ-5.4.1 (MUST):** A report MUST include the hardware manifest, runtime version, model hash, and inference parameters.
- **REQ-5.4.2 (MUST):** A report MUST state whether a deterministic mode
  exists. If it does, it MUST document how to enable it and what
  nondeterminism remains. If it does not, it MUST state why not.
- **REQ-5.4.3 (SHOULD):** Benchmark results SHOULD report variance across at least three runs.

<a id="section-5.5"></a>

### 5.5 Audit trail and remediation

- **REQ-5.5.1 (MUST):** A reported anomaly MUST include a reproduction and
  an inspectable trace.
- **REQ-5.5.2 (MUST):** A report MUST state whether a remediation exists.
  Where none exists, it MUST state the accepted risk and the compensating
  control.
- **REQ-5.5.3 (MUST):** Security-sensitive findings follow [`SECURITY.md`](../../SECURITY.md) until disclosure.

<a id="section-5.6"></a>

### 5.6 Cryptographic storage

This section applies when `stores_data_at_rest` is true. When it is false,
5.6.1–5.6.4 are reported `not_applicable`, with evidence that no
prompt-derived data is written to storage.

- **REQ-5.6.1 (MUST):** Stored data MUST be protected by an authenticated
  envelope: confidentiality plus integrity, with the integrity check
  mandatory on read. A failed check MUST abort the read rather than return
  data. A nonce MUST NOT be reused under the same key. The envelope MUST
  bind the ciphertext to its context (tenant, namespace, item ID), so that
  a valid envelope moved to another context fails the integrity check.
- **REQ-5.6.2 (MUST):** Keys MUST NOT be stored alongside ciphertext in plaintext.
- **REQ-5.6.3 (MUST):** A report MUST state whether key material is derived
  from a user secret. Where it is, key derivation MUST resist offline
  guessing at the cost stated in the report, and the function and parameters
  MUST be recorded.
- **REQ-5.6.4 (MUST):** A report MUST state the algorithm, key size, nonce
  strategy, and, where a key is derived, the derivation function and
  parameters.

<a id="section-5.7"></a>

### 5.7 Supply chain

- **REQ-5.7.1 (MUST):** Dependencies MUST be pinned and recorded in the
  report. Model weights MUST be identified by a cryptographic digest of at
  least 256 bits, with the algorithm named. Conformance MUST NOT require
  publication of model weights or source code; a digest establishes
  identity without disclosure.
- **REQ-5.7.2 (SHOULD):** Releases SHOULD include a digest manifest and a
  machine-readable dependency inventory.
- **REQ-5.7.3 (MUST):** A report MUST state whether the build is
  reproducible. Where it is not, it MUST list each source of deviation.

<a id="section-6"></a>

## 6. Test methods

<a id="section-6.1"></a>

6.1 Each test vector is executed in a declared environment and its result
    recorded. Any mechanism that performs the vector's observation is
    acceptable; the vector names the observation, not an instrument.

<a id="section-6.2"></a>

6.2 A test passes only if the observed outcome matches the vector's
    expected outcome, within any tolerance the vector declares.

<a id="section-6.3"></a>

6.3 A report MUST conform to [`schemas/conformance-report.schema.json`](schemas/conformance-report.schema.json).

<a id="section-6.4"></a>

6.4 Verification MUST NOT require network access after the environment
    named in the test vector has been established.

<a id="section-6.5"></a>

6.5 Every measured quantity MUST have a stated unit, a stated tolerance,
    and a stated method. A quantity without all three is not evidence.

<a id="section-7"></a>

## 7. Report format

The report is JSON, validated by the schema. Required top-level fields: `report_version`, `spec_version`, `capabilities`, `conformance_level`, `subject`, `environment`, `results`, `generated_at`. `harness` is required at L2 and above; `assessment` is required at L1; `categories` is required when `processes_personal_data` is true.

<a id="section-8"></a>

## 8. Security considerations

Threats include telemetry exfiltration, prompt persistence, swap leakage,
core-dump leakage, model substitution, and supply-chain compromise.
Requirements 5.1, 5.2, 5.3, 5.6, and 5.7 address the baseline. A conforming
implementation is not automatically secure.

Out of scope: a compromised host operating system or hypervisor; a
malicious runtime, model, or dependency with the deployment's own
privileges; a user with local or physical access; microarchitectural and
other side channels; traffic analysis by a party that observes the
network; and legal compulsion. The standard measures whether stated
properties hold at the deployment boundary. It does not establish that the
boundary itself is trustworthy.

<a id="section-9"></a>

## 9. Privacy considerations

A deployment can be zero-telemetry and still process personal data. Filtering is not anonymization. Adopters remain responsible for lawful basis and retention.

<a id="section-annex-a"></a>

## Annex A (informative) — Hardware manifest

Suggested fields: CPU/GPU model, instruction sets, RAM, storage class, OS, kernel, container runtime, power profile.

<a id="section-annex-b"></a>

## Annex B (informative) — Test vector format

See [`test-vectors/README.md`](test-vectors/README.md).

<a id="section-annex-c"></a>

## Annex C (informative) — Change history

See [`changelog.md`](changelog.md).
