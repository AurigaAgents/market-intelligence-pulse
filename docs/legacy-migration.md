# Legacy Migration

M0 imports eligible legacy market reports into the public report layout while preserving their weaker provenance status.

Expected source range:

- calendar range: 2026-04-13 through 2026-06-05;
- local date directories: 53;
- missing calendar date: 2026-04-29;
- eligible `legacy-report` directories: 40;
- `legacy-partial-run` directories: 9;
- `legacy-engagement-only` directories: 4.

Legacy reports are public only when they can be represented safely without private runtime data. Partial-run and engagement-only records are summarized here unless a later explicit decision creates a separate archival treatment.

Local import scripts and proof files live under ignored `tmp/legacy-import-YYYYMMDD/` during M0 and are removed after successful verification.
