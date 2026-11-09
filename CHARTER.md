# Charter of the Global Constrained AI Initiative

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Governing instrument.** Where documents conflict, this Charter prevails. It is not a statute or a legal instrument.

## 1. Name and status

1.1 The initiative is the **Global Constrained AI Initiative (GCAII)**.

1.2 GCAII is an **unincorporated research and conformance initiative**. It is not a registered nonprofit, charity, company, or statutory body.

1.3 The term **Secretariat** refers to the interim coordination group that maintains this repository. It does not describe a legal office or an employer.

1.4 GCAII stewards the **GCAII Standards** series. The series is not a separate legal entity.

## 2. Purpose

GCAII exists to make constrained AI deployment verifiable, reproducible, and affordable on local hardware.

It does this by:

- publishing open specifications and policy guidance;
- documenting reproducible audits of transformer layers, quantization runtimes, and edge runtimes;
- maintaining a conformance program that is technical rather than membership-based;
- translating low-level systems work into material that practitioners can reproduce.

## 3. Scope

3.1 **In scope:** sub-billion-parameter language models, GGUF and related inference formats, quantization, attention and state-space architectures, edge memory isolation, telemetry minimization, and reproducible benchmarking.

3.2 **Out of scope:** model training at frontier scale, regulated professional advice, procurement, and certification of legal compliance.

## 4. Principles

### 4.1 Collaborative remediation over critical rhetoric

We do not critique a system without documenting the anomaly and offering a reproducible path to a fix. Where no fix is possible, we state the reason. Criticism without remediation is out of scope.

### 4.2 Equitable knowledge transfer

Low-level internals, quantization boundaries, and tensor layouts should not sit behind gatekeeping. We publish notebooks, test vectors, and explanations that a new practitioner can run.

### 4.3 Persistent open-science utility

Artifacts must outlive commercial cycles. Releases are versioned, archived, and assigned persistent identifiers.

### 4.4 Technical evidence over institutional authority

A claim about runtime behavior is settled by a reproducible test, not by the status of the person making it. Institutional position does not substitute for evidence.

## 5. Document hierarchy

Where documents conflict, the higher item prevails:

1. This Charter
2. Specifications (`specs/`)
3. Policies (`policies/`)
4. Programs (`programs/`)
5. Decision records (`decisions/`)
6. Guidance and templates (`agreements/`, `rfcs/`)

## 6. Standards stewardship

6.1 GCAII publishes specifications under the `GCAII-STD-*` namespace.

6.2 Each specification is versioned with semantic versioning, has a normative body using RFC 2119/8174 keywords, and is archived with a DOI at release.

6.2.1 A release may be published in the repository before its archival deposit is available. That state is recorded as pre-registry in [`documents/registry.yaml`](documents/registry.yaml); 6.2 is satisfied when the DOI is assigned.

6.3 Technical questions are settled by reproducible evidence. Governance questions are settled by the process in [`GOVERNANCE.md`](GOVERNANCE.md).

## 7. Decision-making

7.1 Proposals follow the RFC process in [`rfcs/README.md`](rfcs/README.md).

7.2 Decisions are recorded as ADRs in [`decisions/`](decisions/README.md).

7.3 The decision rule is **rough consensus of maintainers, informed by public comment**, with a recorded fallback vote only when consensus is blocked.

## 8. Amendment

8.1 This Charter may be amended by an RFC that receives:

- a public comment period of at least 14 days;
- approval by two-thirds of active maintainers;
- a recorded ADR and an archived release.

8.2 Amendments take effect only after the new version is published and archived.

## 9. Dissolution

If GCAII ceases operation, maintained documents remain available under their licenses. The repository is archived read-only, and the final release is registered with a DOI.

## 10. Disclaimer

GCAII does not provide legal, security, or regulatory certification. Adopters are responsible for their own compliance. See [`DISCLAIMER.md`](DISCLAIMER.md).
