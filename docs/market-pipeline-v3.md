# Market Pipeline v3

Market Pipeline v3 is a re-entrant, tick-based workflow. Each tick advances ready work, records proof, and exits.

The orchestrator coordinates but does not write substantive market analysis. Analysts, reviewers, assemblers, and publishers work through explicit artifacts and managed issues.

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
