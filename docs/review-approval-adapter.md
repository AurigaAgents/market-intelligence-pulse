# Review Approval Adapter

Market Pulse uses agent review verdicts as the substantive review record. The GitHub App is only a native GitHub adapter: it mirrors a structured, already-recorded `SPC-REVIEW-VERDICT` into an `APPROVE` pull-request review.

## App Contract

Register one GitHub App named `market-pulse-reviewer`.

Required repository permissions:

- Metadata: read
- Issues: read
- Pull requests: write
- Contents: read

Install the app only on `AurigaAgents/market-intelligence-pulse`.

Store these repository secrets:

- `MARKET_PULSE_REVIEWER_APP_ID`
- `MARKET_PULSE_REVIEWER_PRIVATE_KEY`

Set these repository variables:

- `MARKET_PULSE_REVIEWER_APPROVAL_ENABLED=true`
- `MARKET_PULSE_ALLOWED_REVIEW_COMMENTERS=AurigaAgents`
- `MARKET_PULSE_REVIEWER_APP_SLUG=market-pulse-reviewer`

Keep approval disabled until the app is installed and the dry-run workflow has passed for a known PR.

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

The workflow refuses to approve unless all checks pass:

- the verdict comment author is allowlisted;
- the ledger issue has `managed:market-pulse` and `state:review`;
- `Primary reviewer` matches the verdict `reviewer`;
- issue owner and reviewer are different;
- verdict is `approve`;
- PR targets `main` and references the ledger issue;
- PR author is not `market-pulse-reviewer[bot]`;
- PR head SHA matches the verdict `head-sha`, or no commit is newer than the verdict;
- status checks are empty or green;
- PR proof includes validation `status ok`, `errors []`, and privacy/no-private-path proof.

The workflow may run from `issue_comment` events or by manual `workflow_dispatch` with `issue_number` or `pr_number`. Manual runs default to dry-run.

## Branch Protection

`main` should require pull requests and one approving review. Required status checks should stay empty until a real PR validation workflow exists; Pages deployments on `main` are not suitable PR gates.

Recommended branch protection settings:

- required pull request reviews: 1 approval;
- dismiss stale approvals after new commits;
- require last-push approval;
- require conversation resolution;
- disallow force pushes and deletions;
- do not require status checks yet.
