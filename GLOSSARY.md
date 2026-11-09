# Glossary

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Three kinds of term live here, and they are not interchangeable:

- **Normative terms** are load-bearing. They are referenced by `spec.md` and a conformance report depends on their meaning.
- **Project terms** describe how this repository is organised.
- **Background terms** explain domain vocabulary. Nothing in the standard depends on them.

If a normative term is missing or ambiguous, that is a defect in the standard — open an issue.

## Normative terms

These are the terms declared in [`spec.md`](specs/GCAII-STD-0001/spec.md) [Section 3](specs/GCAII-STD-0001/spec.md#section-3). Changing a definition here changes what the standard requires.

| Term | Definition |
|---|---|
| **Deployment boundary** | The set of hardware, storage, and network endpoints under the adopter's operational control for one deployment. The boundary is defined by the adopter, stated in the conformance report, and used to decide whether data has left the system. A cloud API call leaves it; a local socket does not. |
| **Runtime telemetry** | Any data emitted by a running system about its own operation or about the content it processes, and transmitted outside the deployment boundary. Includes prompts, completions, token counts, latency, hardware identifiers, crash reports, usage counters, and features derived from any of these. |
| **Default configuration** | A fresh install with no configuration change, no opt-in, and no account linkage. It is the state a first run produces before the operator acts. |
| **Zero-telemetry** | A configuration in which no runtime telemetry leaves the deployment boundary in the default configuration. |
| **Volatile memory** | Storage whose contents are lost when power is removed — RAM, for example. Swap, hibernation images, and memory-mapped files on persistent storage are **not** volatile. |
| **Conformance report** | The machine-readable record defined by [`conformance-report.schema.json`](specs/GCAII-STD-0001/schemas/conformance-report.schema.json): what was tested, on what environment, against which requirements, with what result. |
| **Harness** | The executable test suite that produces conformance evidence. A harness is not the specification, and passing it is not a guarantee about untested configurations. |
| **Test vector** | A fixed input and its expected output, used to check an implementation's behaviour without re-deriving the expected result each time. |
| **CORE requirement** | A requirement with no capability gate. It applies to every implementation and cannot be excluded by an adopter. The four that define this standard's minimum scope are `REQ-5.1.1`, `REQ-5.1.2`, `REQ-5.1.4`, `REQ-5.2.1`. |
| **CONDITIONAL requirement** | A requirement with a capability gate. It applies only when its declared capability is true. |
| **Capability** | One of the six booleans in `spec.md` [Section 4.7](specs/GCAII-STD-0001/spec.md#section-4.7), declared in every conformance report. The set is closed at this version. |
| **not_applicable** | The result recorded for a requirement whose capability is declared false. It is not a pass, a fail, or a skip, and it requires evidence that the capability is absent. |
| **Evidence of absence** | An inspectable artifact — a listing, a configuration excerpt, or an observed process or device state — showing that a capability is not present. A bare assertion is not evidence. |

## Project terms

| Term | Definition |
|---|---|
| **GCAII** | Global Constrained AI Initiative. The unincorporated research and conformance initiative that stewards this repository. |
| **GCAII Standard** | A document in the `GCAII-STD-*` series stewarded by this project. |
| **GCAII-STD-0001** | The first standard: baseline requirements for constrained, zero-telemetry edge inference. |
| **Secretariat** | The role that keeps the canonical record: it publishes versions, assigns identifiers, and records declarations. It does not approve, certify, accredit, or enforce. |
| **Maintainer** | A contributor with merge and release rights. |
| **Auditor** | A person authorised to review conformance evidence. None is appointed. |
| **Adopter** | An organisation or individual implementing a GCAII standard. |
| **Normative** | A statement that affects conformance. Uses MUST, SHOULD, MAY. |
| **Informative** | Explanatory material that does not affect conformance. |
| **Conformance** | Evidence that an implementation meets the normative requirements of a specific specification version. |
| **Attestation** | A signed statement that a test was run in a described environment. Not a formal proof. |
| **DCO** | Developer Certificate of Origin. A lightweight contribution sign-off. |
| **ADR** | Architecture Decision Record. A dated record of a decision and its reasoning. |
| **RFC** | Request for Comments. A proposal subject to public review. |

## Background terms

Informative only. Nothing in the specification depends on these definitions.

| Term | Definition |
|---|---|
| **SLM** | Small language model. Here, generally sub-billion parameters. |
| **GGUF** | A binary file format for quantised model weights and metadata. |
| **Quantization** | Reducing the numeric precision of weights or activations to lower memory and compute. |
| **tmpfs** | A filesystem stored in volatile memory. Platform-specific. |
| **RSS** | Resident Set Size. The resident memory a process holds. |
| **PPL** | Perplexity. A language-model evaluation metric. |
| **SVD** | Singular value decomposition. |
| **LoRA** | Low-rank adaptation. A parameter-efficient fine-tuning method. |
| **DPO** | Direct Preference Optimization. An alignment method. |
| **SSM** | State-space model. A linear-time sequence architecture. |
| **Mamba** | A selective state-space architecture. |
| **Triton** | A GPU kernel language and compiler. |
