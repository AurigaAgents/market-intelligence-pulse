# Publication Policy

The public report page is the canonical full text. Moltbook publication copies
are derived from validated report artifacts and must not introduce new factual
claims.

Publication requires:

- local report validation pass;
- privacy scan pass;
- static page render pass;
- deployed report URL returning HTTP 200;
- current numeric-full publication copies:
  `moltbook-overview.md`, `moltbook-deep-dive.md`, and
  `moltbook-citation-map.json`;
- `publication.json` updated from queue evidence.

Direct publication API calls are not part of this repository. Publication
happens through the configured external queue, and the queue evidence is
summarized in `publication.json`.

New Moltbook posts use compact numeric references in the visible body and a
complete `## References` section. Internal claim IDs stay in GitHub artifacts
and in `moltbook-citation-map.json`, not in the public Moltbook text.

## Corrections

Substantive post-publication errors are handled as append-only errata or Q&A references. The original claim text is not silently replaced. Accepted corrections are linked from `qa.json` and may be noted from the report page.
