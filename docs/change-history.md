# Documentation Change History

This file is the review ledger for substantive documentation changes.

Project documents remain current-state documents. Obsolete behavior is removed
from the primary documents instead of being preserved inline as historical
architecture. This ledger records why documentation changed and who reviewed
the documentation implications.

Each docs-changing pull request must add or update an entry with:

- date;
- implementation reference;
- documents changed;
- current-state reason;
- reviewer and verdict;
- follow-up, if any.

Entries may be amended within the same pull request after review completes.

## 2026-06-27

### Reviewer Verdict Error-Proof Gate

- Implementation reference: PR #272 and reviewer verdict adapter hardening
  branch `fix/reviewer-verdict-errors-proof`.
- Documents changed: `docs/review-approval-adapter.md` and this file.
- Adapter changed:
  `.github/workflows/market-pulse-reviewer-approval.yml`.
- Current-state reason: align the GitHub reviewer-verdict adapter with the
  guarded local verdict helper. The adapter now treats validation error proof as
  negative-only: explicit non-empty `errors: [...]` blocks approval, while
  `errors: []`, `errors=0`, or absent positive error-list proof do not block a
  reviewer-attested clean validation run.
- Reviewers: Inanna via Trinity Bus review
  `20260627-091917-dione-to-inanna-35036f6e`.
- Verdict: approve.
- Follow-up: align the workflow adapter with the local Python helper for
  multi-line pretty-printed `errors:` lists. The current canonical validator
  output is single-line, so this is not blocking for PR #272.

## 2026-06-18

### Pipeline Hardening Documentation

- Implementation reference: PR #130,
  implementation commit `f1f9ff9dc8407b79e6e0a503a283f02c07b35632`, and this
  documentation governance commit on the same branch.
- Documents changed:
  `docs/market-intelligence-pulse-architecture.md`,
  `docs/review-approval-adapter.md`, `docs/project-control.md`,
  `docs/report-contract.md`, `docs/publication-policy.md`,
  `docs/legacy-migration.md`, `docs/github-pages.md`, and this file.
- Current-state reason: document the guarded review-verdict helper, milestone
  audit, transition timestamp labels, lease-based failover, deterministic agent
  replacement, completed-sentinel success semantics, current Moltbook artifact
  contract, and documentation review rule after a reviewer verdict was posted
  to the wrong pull request.
- Reviewers: Dione via Trinity Bus review
  `20260618-143910-nisaba-to-dione-031b3bf2`; Inanna via Trinity Bus review
  `20260618-144420-nisaba-to-inanna-eb89980d`.
- Verdict: approve.
- Follow-up: none.

### Documentation Status Adapter

- Implementation reference: PR #130 and the adapter workflow commit on this
  branch.
- Documents changed: `docs/market-intelligence-pulse-architecture.md`,
  `docs/review-approval-adapter.md`, and this file.
- Adapter changed:
  `.github/workflows/market-pulse-reviewer-approval.yml`.
- Current-state reason: let reviewed documentation-only and
  documentation-governance PRs satisfy the required
  `market-pulse/reviewer-verdict` status from the review ledger in
  `docs/change-history.md`, without requiring an unrelated managed report
  issue or a manual status bypass.
- Reviewers: Inanna via Trinity Bus review
  `20260618-150958-nisaba-to-inanna-5dc67ab8`; Dione via Trinity Bus review
  `20260618-151604-nisaba-to-dione-9a24fc9d`.
- Verdict: approve.
- Follow-up: none.
