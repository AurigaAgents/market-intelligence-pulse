# Market Intelligence Pulse v3

Market Intelligence Pulse v3 is a re-entrant, tick-based workflow. Each tick advances ready work, records proof, and exits.

The orchestrator coordinates but does not write substantive market analysis. Analysts, reviewers, assemblers, and publishers work through explicit artifacts and managed issues.

## How It Works

### First Nightly Run: Best-Case Dry Run

This scenario describes the first enabled night-window run after Monday
2026-06-15. The active cron job is `market-intelligence-pulse-orchestrator`
with schedule `5,20,35,50 0-6 * * *` in `Europe/Berlin` and command:

```bash
python3.14 /Users/u2ai/OpenClaw/scripts/market_intelligence_pulse_run_daily_pipeline.py \
  --repo AurigaAgents/market-intelligence-pulse \
  --json tick --date auto --dispatch-limit 1
```

Assumptions for the dry run:

- no older incomplete `Pulse YYYY-MM-DD` milestone exists;
- no new issue or pull request is created between the current repo state and
  the first tick, so the illustrative issue numbers below are expected but not
  part of the contract;
- the first M1 night run covers daily ledger creation and segment dispatch only;
  assembly and publication issues are not created by the current orchestrator.

At 2026-06-16 00:05 Berlin, `--date auto` selects report date `2026-06-15`
from `previous-berlin-calendar-day`. The tick contract check passes, required
labels already exist, the local tick lock is acquired, and milestone `Pulse
2026-06-15` is created. If no other milestone was created first, it is expected
to become milestone #3.

The same tick creates the daily ledger issues:

- expected #29: `2026-06-15 pulse control`
  - labels include `state:active`, `type:ops`, `area:report`, `priority:p0`;
  - owner is `Market Pulse Orchestrator`;
  - reviewers are Dione, Inanna, and Nisaba;
  - this issue stays open as the daily coordination and proof ledger.
- expected #30: `2026-06-15 us analysis cycle 1`
  - labels include `state:ready`, `type:analysis`, `area:us`,
    `owner:dione`, `review:nisaba`;
  - expected artifacts:
    `reports/2026/06/15/segments/us/cycle-1/analysis.md`,
    `sources.yaml`, and `claims.jsonl`.
- expected #31: `2026-06-15 eu analysis cycle 1`
  - labels include `state:ready`, `type:analysis`, `area:eu`,
    `owner:dione`, `review:inanna`;
  - expected artifacts live under
    `reports/2026/06/15/segments/eu/cycle-1/`.
- expected #32: `2026-06-15 asia analysis cycle 1`
  - labels include `state:ready`, `type:analysis`, `area:asia`,
    `owner:inanna`, `review:nisaba`;
  - expected artifacts live under
    `reports/2026/06/15/segments/asia/cycle-1/`.
- expected #33: `2026-06-15 macro analysis cycle 1`
  - labels include `state:ready`, `type:analysis`, `area:macro`,
    `owner:dione`, `review:nisaba`;
  - expected artifacts live under
    `reports/2026/06/15/segments/macro/cycle-1/`.
- expected #34: `2026-06-15 sentiment analysis cycle 1`
  - labels include `state:ready`, `type:analysis`, `area:sentiment`,
    `owner:inanna`, `review:dione`;
  - expected artifacts live under
    `reports/2026/06/15/segments/sentiment/cycle-1/`.

After issue creation, the tick reconciles old private leases, creates no retry
issues in the best case, runs `validate-state`, and dispatches one ready segment
because `--dispatch-limit 1` is active. Ready segment issues are sorted by issue
number, so the first dispatch is expected #30, the US segment. The lease helper
comments a public lease on #30 and transitions it from `state:ready` to
`state:active`. The orchestrator then starts a private OpenClaw worker:

```bash
openclaw agent --agent dione --session-id <private-session-id> \
  --timeout 900 --json --message <redacted task prompt>
```

Dione reads #30 as the task contract, creates or reuses branch
`issue-30-2026-06-15-us-analysis-cycle-1`, writes only the three expected US
artifact files, runs the local validation command, opens or updates a PR whose
body references `Fixes #30`, and transitions #30 from `state:active` to
`state:review` with the PR number. On the next tick after that transition,
`reconcile-leases` records the public lease as completed.

Subsequent cron ticks resume the same open `Pulse 2026-06-15` milestone and
dispatch one additional ready segment each time:

- 00:20 Berlin: expected #31, EU, owner Dione, reviewer Inanna;
- 00:35 Berlin: expected #32, Asia, owner Inanna, reviewer Nisaba;
- 00:50 Berlin: expected #33, Macro, owner Dione, reviewer Nisaba;
- 01:05 Berlin: expected #34, Sentiment, owner Inanna, reviewer Dione.

The current orchestrator limits dispatch per tick, not per owner. If a previous
worker is still active, the next ready segment may still be dispatched on the
next 15-minute tick. Each worker follows the same lifecycle:

1. `state:ready -> state:active` when the orchestrator starts the lease.
2. Owner produces the segment artifacts on a branch and opens a PR.
3. Owner runs local validation and records proof in the PR.
4. Owner transitions the issue `state:active -> state:review` with the PR
   number.
5. Reviewer audits the issue, PR, artifacts, sources, claims, proof, and
   privacy surface.
6. Reviewer posts one `SPC-REVIEW-VERDICT` issue comment with `verdict:
   approve`, the PR number, and exact head SHA.
7. The GitHub workflow validates the verdict and writes the required
   `market-pulse/reviewer-verdict` commit status on the PR head SHA.
8. After the green status, the PR is mergeable. The segment issue can then be
   treated as accepted.

The helper-supported acceptance marker is `state:review -> state:ready` after
the required reviewer approval comment exists. In this accepted state, the issue
is not dispatched again if its linked PR exists. During the M1 night run,
segment issues should stay open until all ready segments have been dispatched,
or until `validate-state` is extended to count closed accepted issues. Closing a
segment issue too early would make the current validator, which reads open
issues, report that expected issue as missing on the next tick.

In the best-case M1 close-out, all five segment PRs are reviewed, the required
`market-pulse/reviewer-verdict` statuses are green, and the PRs are merged. The
daily control issue records compact public-safe proof: tick output, validation
status, dispatched issue list, PR links, reviewer verdict links, and merge
links. Only after the segment dispatch wave is complete should segment issues,
the control issue, and the milestone be closed if no downstream assembly issue
exists yet.

Downstream assembly and publication are deliberately separate. When enabled, a
later orchestrator phase will create managed `type:assembly` and
`type:publication` issues after the segment artifacts are accepted. Until that
phase exists, the first nightly run proves the GitHub-ledger segment pipeline;
it does not publish a final Market Pulse report by itself.

## Automatic Catch-up

The unattended tick uses `--date auto`.

1. Explicit `--date YYYY-MM-DD` wins.
2. Otherwise, the tick searches a short lookback window for incomplete `Pulse YYYY-MM-DD` milestones.
3. The oldest incomplete milestone is resumed before a new date is started.
4. This is ledger-based catch-up through the same state machine, not a retry sweeper.

## Guardrails

- maximum segment cycles per segment per report date: 3;
- maximum open production issues per daily milestone: 40, excluding `type:qa`;
- maximum open `type:qa` issues per daily milestone: 25;
- maximum blocking revision cycles before owner escalation: 2.
