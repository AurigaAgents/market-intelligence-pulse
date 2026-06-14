# Orchestrator State Machine

```mermaid
stateDiagram-v2
    [*] --> Ready: orchestrator creates artifact issue
    Ready --> Active: orchestrator dispatches owner and sets lease
    Active --> Review: owner opens or updates PR with artifact and local proof
    Active --> Blocked: owner reports blocker or lease expires
    Review --> Accepted: required reviewers approve and local gates pass
    Review --> Blocked: reviewer blocks with exact correction
    Review --> NeedsDecision: policy, scope, source, or publication decision needed
    Blocked --> Ready: blocker resolved or next cycle issue created
    NeedsDecision --> Ready: control decision accepted
    Accepted --> Closed: orchestrator records proof and opens downstream issue
    Closed --> [*]
```

State labels are changed only through the shared project-control helper. Free-text comments may explain a verdict, but native pull request review state is the machine-readable approval signal for PR-backed artifacts.

Leases are public-safe issue comments. Tick locks are private local runtime state and are not stored in this repository.
