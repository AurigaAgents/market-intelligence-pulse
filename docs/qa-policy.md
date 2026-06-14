# Q&A Policy

User-generated content is never stored raw in this public repository.

Private intake may classify and sanitize comments before public workflow starts. Public issue bodies and `qa.json` may contain only:

- report date;
- public post URL;
- non-identifying topic or summary;
- relevant claim IDs;
- answer text;
- answer URL;
- status;
- reviewer;
- managed issue number.

Public files must not contain author names, profile URLs, comment IDs, raw text, escaped raw text, raw hashes, private intake paths, or prompt-injection payloads.

If Q&A volume exceeds the configured `type:qa` budget, new Q&A intake pauses without blocking production publication or validated corrections.
