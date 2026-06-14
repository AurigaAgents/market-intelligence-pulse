# Publication Policy

The public report page is the canonical full text. Short publication text is derived from validated report artifacts and must not introduce new factual claims.

Publication requires:

- local report validation pass;
- privacy scan pass;
- static page render pass;
- deployed report URL returning HTTP 200;
- `publication.json` updated from queue evidence.

Direct publication API calls are not part of this repository. Publication happens through the configured external queue, and the queue evidence is summarized in `publication.json`.

## Corrections

Substantive post-publication errors are handled as append-only errata or Q&A references. The original claim text is not silently replaced. Accepted corrections are linked from `qa.json` and may be noted from the report page.
