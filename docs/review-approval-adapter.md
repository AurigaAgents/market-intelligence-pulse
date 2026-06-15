# Review Approval Adapter

Market Pulse uses agent review verdicts as the substantive review record. The workflow is the native GitHub adapter: it validates a structured, already-recorded `SPC-REVIEW-VERDICT`, writes the required `market-pulse/reviewer-verdict` commit status on the PR head SHA, and optionally mirrors the verdict into an `APPROVE` pull-request review for audit visibility.

## App Contract

Register one GitHub App named `market-pulse-reviewer`.

Required repository permissions:

- Metadata: read
- Issues: read
- Pull requests: write
- Contents: read

Install the app only on `AurigaAgents/market-intelligence-pulse`.

The workflow also needs `GITHUB_TOKEN` permission `statuses: write` so it can publish the required commit status.

Store these repository secrets:

- `MARKET_PULSE_REVIEWER_APP_ID`
- `MARKET_PULSE_REVIEWER_PRIVATE_KEY`

Set these repository variables:

- `MARKET_PULSE_REVIEWER_APPROVAL_ENABLED=true`
- `MARKET_PULSE_ALLOWED_REVIEW_COMMENTERS=AurigaAgents`
- `MARKET_PULSE_REVIEWER_APP_SLUG=market-pulse-reviewer`
- `MARKET_PULSE_REVIEW_STATUS_CONTEXT=market-pulse/reviewer-verdict` (optional; this is the default)

Keep approval disabled until the app is installed and the dry-run workflow has passed for a known PR.

Bootstrap note: the adapter workflow is only available as default-branch automation after its PR is merged. The first merge of the adapter or its branch-protection migration therefore needs an explicit maintainer/admin bypass or another already-working gate. After that, the required status check is the merge gate.

## Verdict Format

Preferred issue comment:

```text
SPC-REVIEW-VERDICT
reviewer: inanna
verdict: approve
scope: validation-public-safety
pr: #19
head-sha: 83bc4b13378be85d2e1b4905aaf410b3ae4a6786
```

`head-sha` is preferred. If it is absent, the adapter falls back to checking that no PR commit is newer than the verdict comment.

## Adapter Gates

The workflow refuses to mark `market-pulse/reviewer-verdict` successful unless all checks pass:

- the verdict comment author is allowlisted;
- the ledger issue has `managed:market-pulse` and `state:review`;
- `Primary reviewer` matches the verdict `reviewer`;
- issue owner and reviewer are different;
- verdict is `approve`;
- PR targets `main` and references the ledger issue;
- PR author is not `market-pulse-reviewer[bot]`;
- PR head SHA matches the verdict `head-sha`, or no commit is newer than the verdict;
- status checks are empty or green, excluding the adapter's own `market-pulse/reviewer-verdict` context while it refreshes that status;
- PR proof includes validation `status ok`, `errors []`, and privacy/no-private-path proof.

When validation fails after the PR head SHA is known, the workflow writes `market-pulse/reviewer-verdict: failure` so a stale success on the same SHA is overwritten. If a matching `market-pulse-reviewer[bot]` approval already exists for the current head SHA, the workflow refreshes the commit status but skips creating a duplicate approval review.

The workflow may run from `issue_comment` events or by manual `workflow_dispatch` with `issue_number` or `pr_number`. Manual runs default to dry-run.

## Branch Protection

`main` should use the reviewer verdict commit status as the machine gate. GitHub App pull-request approvals remain useful audit proof, but they do not satisfy required-review branch protection for this user-owned repository.

Recommended branch protection settings:

- require status checks before merging;
- required check: `market-pulse/reviewer-verdict`;
- strict status checks: false, unless the project explicitly wants every PR branch rebased after unrelated `main` changes;
- required pull request reviews: disabled as a gate for agent-reviewed Market Pulse artifacts;
- require conversation resolution;
- disallow force pushes and deletions;
- do not use Pages deployments on `main` as PR gates.
