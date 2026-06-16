# Orchestrator State Machine

```mermaid
stateDiagram-v2
    [*] --> Ready: orchestrator creates artifact issue
    Ready --> Active: orchestrator dispatches owner and sets lease
    Active --> ReviewRequested: owner opens PR with artifacts, proof, PR milestone, and standard PR shape
    Active --> Ready: owner lease fails before a usable PR exists
    Active --> Blocked: owner reports a substantive blocker or PR handoff gate fails
    ReviewRequested --> Review: orchestrator dispatches reviewer and records review lease
    Review --> ReviewRequested: review lease fails before verdict
    Review --> Accepted: reviewer approves and reviewer-verdict status is green
    Review --> Blocked: reviewer blocks with exact correction
    Review --> NeedsDecision: policy, scope, source, or publication decision needed
    Blocked --> Ready: operational blocker resolved on the same issue
    Blocked --> Ready: next cycle issue created only after reviewer block on delivered work
    NeedsDecision --> Ready: control decision accepted
    Accepted --> Closed: orchestrator records proof and opens downstream issue
    Closed --> [*]
```

State labels are changed only through the shared project-control helper.
`state:review-requested` means the owner is done and a reviewer must now be
dispatched; `state:review` means a named reviewer has actually accepted a
review lease and is working. Free-text comments may explain a verdict, but the
machine-readable acceptance gate is the structured `SPC-REVIEW-VERDICT`
combined with a successful `market-pulse/reviewer-verdict` commit status.

Leases are public-safe issue comments. Tick locks are private local runtime state and are not stored in this repository.
