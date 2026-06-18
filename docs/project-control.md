# Project Control

Market Intelligence Pulse uses managed GitHub issues, pull requests,
milestones, labels, review states, and structured ledger comments after M0
bootstrap completes.

M0 itself is a local bootstrap checklist, not a project-control milestone.

## Managed Labels

- `role:project-scribe`
- `role:implementation-owner`
- `role:architecture-reviewer`
- `role:validation-reviewer`
- `role:data-reviewer`
- `role:status-reporter`
- `state:ready`
- `state:active`
- `state:review-requested`
- `state:review`
- `state:accepted`
- `state:blocked`
- `state:needs-decision`
- `type:analysis`
- `type:review`
- `type:assembly`
- `type:publication`
- `type:qa`
- `type:ops`
- `area:us`
- `area:eu`
- `area:asia`
- `area:macro`
- `area:sentiment`
- `area:report`
- `area:moltbook`
- `area:qa`
- `risk:data`
- `risk:publication`
- `risk:privacy`
- `risk:ops`
- `priority:p0`
- `priority:p1`
- `priority:p2`
- `owner:dione`
- `owner:inanna`
- `owner:nisaba`
- `review:dione`
- `review:inanna`
- `review:nisaba`
- `decision:ingo`
- `decision:agent-review`
- `platform:openclaw-local`
- `managed:market-pulse`

The orchestrator and project-control helper may also create dynamic audit
labels:

- `since:<STATE_CODE>:<YYYYMMDDTHHMMSSZ>` for the current state entry time;
- `t:<FROM_CODE>-<TO_CODE>:<YYYYMMDDTHHMMSSZ>` for each state transition;
- `agent-replaced:<owner|reviewer>:<YYYYMMDDTHHMMSSZ>` for deterministic
  failover after repeated expired leases.

Dynamic audit labels are an index for GitHub queries. The structured issue
comments remain the durable explanation.

## Responsibility Block

Managed issues include:

```text
## Responsibility
Owner:
Primary reviewer:
Decision owner:
Milestone:
Target platform:
Due:
Current next action:
Proof required:
```

Automation ignores issues and pull requests that do not carry the managed labels and responsibility block.

## State Transition Audit

State labels are changed only through `software_project_control.py` or the
orchestrator paths that call it. Each transition must leave a
`MARKET-PULSE-STATE-TRANSITION` issue comment with the previous state, new
state, actor, timestamp, and, when applicable, PR, head SHA, lease token, and
reason.

Each open managed issue should have exactly one current `since:*` label whose
state code matches its single `state:*` label. Transition history labels
(`t:*`) are append-only audit indexes and are not edited by hand.

Agent replacement is allowed only after repeated expired leases for the same
role on the same issue. The replacement updates the owner or reviewer label,
updates the responsibility block, adds an `agent-replaced:*` label, and records
`MARKET-PULSE-AGENT-REPLACEMENT`.

## Artifact PR Contracts

Managed artifact PRs use standard title forms for new unattended runs:

```text
feat(<segment>): add <YYYY-MM-DD> <segment> analysis cycle <N>
feat(report): assemble <YYYY-MM-DD> market pulse cycle <N>
feat(publication): publish <YYYY-MM-DD> market pulse cycle <N>
```

The PR milestone must match the managed issue milestone, for example `Pulse
2026-06-15`.

The segment title form is enforced by the shared project-control helper.
Assembly and publication title forms are enforced by the orchestrator's reviewer
handoff validation for newly managed issues. Older manual recovery PRs may use
`fix(...)` or `chore(...)` titles and remain historical records.

PR bodies must include these top-level sections in this order:

- `## Summary`
- `## Expected artifacts`
- `## Source and claim counts`
- `## Validation proof`
- `## Privacy proof`
- `## Reviewer`

The body must also contain `Fixes #<issue>`.

## Review Verdict Posting

Reviewer agents use the guarded verdict helper in normal operation:

```bash
python3.14 $OPENCLAW_ROOT/scripts/market_intelligence_pulse_post_review_verdict.py \
  --repo AurigaAgents/market-intelligence-pulse \
  --issue <issue-number> \
  --pr <pr-number> \
  --reviewer <dione|inanna|nisaba> \
  --verdict approve \
  --head-sha <exact-pr-head-sha> \
  --evidence-file <review-evidence.md>
```

The helper posts `SPC-REVIEW-VERDICT` only to the managed ledger issue after it
has verified the issue, PR, reviewer assignment, milestone, owner/reviewer
separation, head SHA, and required proof. Raw `gh issue comment` and PR
comments are for recovery and debugging, not the normal reviewer path.
