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
