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
- Adapter changed:
  `.github/workflows/market-pulse-reviewer-approval.yml`.
- Current-state reason: document the guarded review-verdict helper, milestone
  audit, transition timestamp labels, lease-based failover, deterministic agent
  replacement, completed-sentinel success semantics, current Moltbook artifact
  contract, documentation review rule, and docs/change-history-based status gate
  after a reviewer verdict was posted to the wrong pull request and a reviewed
  documentation PR had no machine-visible status.
- Reviewers: Dione via Trinity Bus review
  `20260618-143910-nisaba-to-dione-031b3bf2`; Inanna via Trinity Bus review
  `20260618-144420-nisaba-to-inanna-eb89980d`; Inanna adapter-gate review
  `20260618-150958-nisaba-to-inanna-5dc67ab8`.
- Verdict: approve.
- Follow-up: none.
