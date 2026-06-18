# Legacy Migration

Legacy migration records the already-imported pre-ledger market reports and
their weaker provenance status. It does not define the contract for new daily
runs.

Expected source range:

- calendar range: 2026-04-13 through 2026-06-05;
- local date directories: 53;
- missing calendar date: 2026-04-29;
- eligible `legacy-report` directories: 40;
- `legacy-partial-run` directories: 9;
- `legacy-engagement-only` directories: 4.

Legacy reports are public only when they can be represented safely without
private runtime data. Partial-run and engagement-only records remain out of the
normal report contract unless a later explicit decision creates a separate
archival treatment.

Local import scripts and proof files lived under ignored
`tmp/legacy-import-YYYYMMDD/` during M0 and were removed after successful
verification. They are not part of the active pipeline.
