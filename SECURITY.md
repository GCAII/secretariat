# Security Policy

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

## Supported versions

Only the latest released version of each specification and harness is supported with security fixes. Older versions remain available for provenance but are not patched.

## Reporting a vulnerability

Do **not** open a public issue for a suspected vulnerability.

- Email: `gcaii.secretariat@outlook.com`
- Subject line: `[GCAII security] <short description>`
- Include: affected version, reproduction steps, impact, and whether you intend to publish.

Reports go to the single project mailbox with the `[GCAII security]` tag. There is no `security@` address on a project domain because no project domain is registered; this page is updated when one is.

You will receive an acknowledgement within 7 days. We aim to provide an initial assessment within 14 days and a fix or mitigation within 90 days, best effort. This is a volunteer project; these are targets, not contractual commitments.

## Scope

In scope:

- The conformance harness and its test vectors.
- Reference implementations published under GCAII.
- Specification requirements that could cause a security failure when implemented as written.
- Repository infrastructure (CI, release signing, registry integrity).

Out of scope:

- Third-party models, runtimes, or hardware.
- Vulnerabilities that require a compromised host.
- Legal or regulatory compliance questions.

## Disclosure

We follow coordinated disclosure:

1. Report privately.
2. We confirm and assess.
3. We prepare a fix and an advisory.
4. We publish the advisory with credit, unless you ask to remain anonymous.
5. If a fix is not possible within 90 days, we publish a mitigation and a timeline.

We will not pursue legal action against good-faith research that follows this policy.

## Safe harbor

Good-faith testing of your own deployment, or of the harness in a controlled environment, is authorized. Do not test third-party systems, do not access data you do not own, and do not degrade availability.

## Security expectations for adopters

- Verify release hashes from [`documents/registry.yaml`](documents/registry.yaml).
- Pin harness versions in conformance reports.
- Treat conformance as evidence about a tested configuration, not a guarantee for every deployment.
