# Project Control

Market Intelligence Pulse uses managed GitHub issues, pull requests, milestones, labels, and review states after M0 bootstrap completes.

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
