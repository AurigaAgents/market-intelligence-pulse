# Report Contract

Each report date is stored under `reports/YYYY/MM/DD/`.

Required files for new reports:

- `index.html`
- `report.md`
- `overview.md`
- `deep-dive.md`
- `sources.yaml`
- `claims.jsonl`
- `manifest.json`
- `publication.json`
- `qa.json`
- `moltbook.md`

Segment work is stored under `segments/<segment>/cycle-N/` with analysis, review, source, claim, and review metadata files.

## Fact Boundary

Every factual statement in report text must map to a claim ID or be explicitly marked as inference or editorial framing. Writers and extractors must not introduce unsupported facts while assembling or shortening text.

Legacy reports may omit claim-level ledgers only when `manifest.json` sets:

```json
{
  "legacy": true,
  "coverage": "legacy-aggregate",
  "legacy_import_class": "legacy-report"
}
```
