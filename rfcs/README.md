# Requests for Comments (RFCs)

> **Status:** Active · **Version:** 1.0.0 · **Date:** 2026-11-08

An RFC is the way to propose a normative or structural change. Editorial fixes do not need one.

## Process

1. Copy [`0000-template.md`](0000-template.md) to `NNNN-short-title.md`.
2. Open a pull request with status `draft`.
3. Announce a public comment period of at least 14 days for normative changes.
4. Revise; summarize objections and unresolved points.
5. Maintainers seek rough consensus under [`GOVERNANCE.md`](../GOVERNANCE.md).
6. Record the outcome as an ADR in [`decisions/`](../decisions/README.md).
7. Merge with status `accepted` or `rejected`.

## Statuses

| Status | Meaning |
|---|---|
| `draft` | Under author revision; not open for decision |
| `proposed` | Open for public comment |
| `accepted` | Approved; implementation may proceed |
| `rejected` | Not accepted; rationale recorded |
| `withdrawn` | Author withdrew it |
| `implemented` | Merged into a released version |

## Rules

- One RFC, one change.
- Link the requirements affected.
- State backward compatibility.
- Include a test plan for normative changes.
- Do not edit an accepted RFC; supersede it with a new one.
