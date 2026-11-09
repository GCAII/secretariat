# Audit Program

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

## 1. Purpose

Define who may perform an independent conformance audit and how independence is protected.

## 2. Auditor qualifications

An auditor should have:

- demonstrated experience with inference runtimes, quantization, or systems security;
- familiarity with the specification and harness;
- no undisclosed commercial interest in the audited implementation;
- a public identity and a way to verify their work.

There is no formal accreditation yet. Until one exists, appointment is by maintainer consensus and is recorded in [`MAINTAINERS.md`](../MAINTAINERS.md).

## 3. Independence

- The auditor must not be employed by, consulting for, or financially interested in the submitter.
- The auditor must not have contributed the code being audited, beyond test vectors.
- A disclosed relationship may be acceptable for L2 but not L3.
- Recusal is mandatory when independence is in doubt.

## 4. Method

1. Review the report and schema validity.
2. Verify hashes and signatures.
3. Re-run the harness in a second environment.
4. Inspect the evidence for each MUST.
5. Sample test vectors; do not trust a summary.
6. Record limitations and deviations.
7. Publish an attestation with the report.

## 5. Report

An audit attestation includes:

- auditor identity and independence statement;
- specification and harness versions;
- environments tested;
- requirements checked and results;
- limitations and unresolved questions;
- signature and date.

## 6. Conflicts and removal

An auditor with a conflict must recuse. Repeated failure to disclose a conflict, or a finding that is not reproducible, is grounds for removal by maintainer consensus after an appealable process.

## 7. Compensation

Auditors may charge for their time. GCAII does not set rates and does not receive a share. A paid audit does not change the technical result.
