# Cryptography Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08
> **Elaborates:** REQ-5.6.1 – REQ-5.6.4

## 1. Purpose

Define baseline expectations for encrypted local storage of prompts, sessions, and indexes.

## 2. Requirements

This section applies when `stores_data_at_rest` is true. When it is false,
crypto-P1 – crypto-P6 are reported `not_applicable`, with evidence that no
prompt-derived data is written to storage.

- **crypto-P1 (MUST):** Stored data is protected by an authenticated
  envelope: confidentiality plus integrity, with the integrity check
  mandatory on read. A failed check MUST abort the read.
- **crypto-P2 (MUST):** Keys are not stored alongside ciphertext in plaintext.
- **crypto-P3 (MUST):** Nonces are unique per key; never reused.
- **crypto-P4 (MUST):** The report states whether key material is derived
  from a user secret. Where it is, key derivation resists offline guessing
  at the cost stated in the report, and the function and parameters are
  recorded.
- **crypto-P5 (MUST):** Associated data binds ciphertext to its context
  (tenant, namespace, item ID), so that an envelope moved to another context
  fails its integrity check.
- **crypto-P6 (MUST):** The report states algorithm, key size, nonce
  strategy, and, where a key is derived, the derivation function and
  parameters.

Deletion of stored data is outside this section. An adopter that offers
deletion states its method in its documentation; the standard does not
require a particular erasure guarantee, because such a guarantee is a
property of the storage medium and the operator, not of the envelope.

## 3. Threat model

In scope: stolen disk, backup leakage, file swap between contexts, accidental retention.

Out of scope: a compromised OS, a malicious runtime with memory access, side-channel attacks on the CPU, and legal compulsion.

## 4. Anti-patterns

- AES-CBC without a MAC.
- A constant nonce.
- A key derived from a passphrase with one iteration.
- Storing the wrapped key in the same directory as the ciphertext without a separate trust boundary.
- "Military-grade" as a description.

## 5. Verification

Each step tests an outcome at the storage boundary, not a library call.

- Round-trip: stored then read returns the original plaintext.
- Tamper: any single-bit modification of the stored envelope causes the
  read to fail rather than return data.
- Substitution: an envelope moved between namespaces or records fails its
  integrity check.
- Nonce: two encryptions under the same key produce distinct nonces; the
  report states how uniqueness is guaranteed.
- Derivation: the measured unlock cost is reported with the parameters.

## 6. Conforming examples (informative)

The following satisfy section 2. They are examples, not requirements. Any
construction meeting the outcome invariants is conforming.

- AES-256-GCM (NIST SP 800-38D)
- ChaCha20-Poly1305 (RFC 8439)
- Any authenticated encryption with a non-repeating nonce and an integrity tag

Key derivation examples: Argon2id (RFC 9106), scrypt (RFC 7914),
PBKDF2-HMAC with a stated work factor (RFC 8018).

## 7. References

- [`specs/GCAII-STD-0001/spec.md`](../specs/GCAII-STD-0001/spec.md) [Section 5.6](../specs/GCAII-STD-0001/spec.md#section-5.6)
- NIST SP 800-38D (GCM) — example, not a requirement
- RFC 8439 (ChaCha20-Poly1305) — example, not a requirement
- RFC 9106 (Argon2) — example, not a requirement
