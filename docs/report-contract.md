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
- `moltbook-overview.md`
- `moltbook-deep-dive.md`
- `moltbook-citation-map.json`

Segment work is stored under `segments/<segment>/cycle-N/` with:

- `analysis.md`
- `sources.yaml`
- `claims.jsonl`

The merged top-level report chooses the accepted segment cycle through
`manifest.json`.

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

Legacy reports imported before the numeric-full Moltbook renderer may contain
`moltbook.md` instead of the two current Moltbook publication copies and
citation map. That exception does not loosen the contract for new reports.
