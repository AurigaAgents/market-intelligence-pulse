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
- `state:review`
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
