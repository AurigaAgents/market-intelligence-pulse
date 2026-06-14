# Trading Calendar

The report directory date is the selected report date. In normal unattended operation this is the previous Europe/Berlin calendar date. Automatic catch-up or explicit `--date YYYY-MM-DD` may target an earlier incomplete report.

Per-claim market sessions are recorded using source-local `as_of` and `market_session` fields.

Holiday handling:

- days with no covered market session may produce a no-regular-report status;
- mixed holidays mark closed segments explicitly;
- weekly, month-to-date, and year-to-date calculations must state calendar and session basis.
