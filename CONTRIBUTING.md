# Contributing to GCAII

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

Thanks for helping. This repository holds standards and governance documents, so the bar is evidence and precision, not volume.

## 1. Ways to contribute

- **Editorial:** fix typos, clarify wording, improve links.
- **Normative:** add or change a requirement in `specs/`.
- **Evidence:** contribute test vectors, benchmark results, or a reproduction report.
- **Policy:** propose guidance in `policies/`.
- **Process:** improve templates, CI, or governance.

Normative changes need an RFC. Editorial changes can go straight to a pull request.

## 2. Before you start

- Read [`CHARTER.md`](CHARTER.md) and [`GOVERNANCE.md`](GOVERNANCE.md).
- For a substantial change, open an issue or draft an RFC first.
- For a security issue, do **not** open a public issue; see [`SECURITY.md`](SECURITY.md).

## 3. Pull requests

1. Fork the repository and create a branch.
2. Make the smallest coherent change.
3. Update the changelog if the change is user-visible.
4. Add or update test vectors if the change is normative.
5. Sign off your commits with the Developer Certificate of Origin:

   ```text
   Signed-off-by: Your Name <you@example.com>
   ```

6. Open a pull request using the template.
7. Address review comments; do not force-push after review starts unless asked.

## 4. Normative language

Specifications use RFC 2119 and RFC 8174 keywords:

- **MUST / MUST NOT** — absolute requirement.
- **SHOULD / SHOULD NOT** — recommended; deviations need a recorded reason.
- **MAY** — optional.

Do not use "must" in lowercase for a requirement. Do not use "encouraged" in a normative document; it is not testable.

## 5. Style

- Markdown, one sentence per line is welcome but not required.
- Use ATX headings (`##`), fenced code blocks with a language tag, and relative links.
- Prefer plain language over jargon; define a term in [`GLOSSARY.md`](GLOSSARY.md) on first use.
- Do not add tracking pixels, remote images, or embedded scripts.

## 6. Review

- Editorial: one maintainer approval.
- Normative: one maintainer plus a 14-day comment period.
- Conformance-affecting: one maintainer plus one auditor.

Review is about correctness and reproducibility, not seniority.

## 7. Licensing of contributions

By contributing, you agree that your contribution is licensed under the terms in [`LICENSING.md`](LICENSING.md). At 1.0.0, all material is CC BY 4.0. When the split takes effect, code and harnesses will be Apache-2.0 and test vectors and schemas CC0 1.0.

You retain copyright; you grant the project a perpetual, worldwide, non-exclusive license under those terms. See [`LICENSE`](LICENSE).

## 8. Code of conduct

Participation is governed by [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md). Technical disagreement is welcome; harassment is not.
