# Source Policy

New reports use `sources.yaml` and `claims.jsonl` as the factual ledger.

`sources.yaml` records citation metadata. `claims.jsonl` records claims and their source references. Claim-to-source links are authoritative in `claims.jsonl[].source_refs[]`; generated source indexes are derived and are not committed.

## Source Rules

- Use primary sources where possible for economic releases, central-bank decisions, rates, and official data.
- News sources may support market interpretation and attribution.
- Paywalled sources may be cited as metadata, but copied article text is not stored here.
- Live or mutable pages must record retrieval method and mutability.
- Numeric market claims must include timestamp or session basis.

## Numeric Review Overrides

Small provider-basis differences may pass only through a claim-specific `numeric_overrides[]` entry in `review.json`. Overrides must include reported value, recomputed value, absolute delta, provider basis, reviewer, timestamp, and allowed justification. Arithmetic errors, stale quotes, missing bases, or unsupported values remain blockers.
