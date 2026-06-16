# Market Intelligence Pulse

Source-backed market reports and publication metadata for Market Intelligence Pulse.

This repository is a public report container. It stores reports, source and claim ledgers, publication metadata, sanitized Q&A references, static GitHub Pages output, schemas, templates, and issue templates.

Execution stays outside this repository. Runtime scripts, validators, renderers, import tools, agent prompts, local state, credentials, and private intake data are not committed here.

## Architecture

The canonical workflow description is
[`docs/market-intelligence-pulse-architecture.md`](docs/market-intelligence-pulse-architecture.md).
It explains the end-to-end architecture, state model, phases, scripts, skills,
validation gates, review gates, and Moltbook publication flow.

## Status

Active GitHub-ledger workflow.

The repository is the public report and audit container for the current
Market Intelligence Pulse workflow. Daily production is coordinated by managed
GitHub milestones, issues, pull requests, review verdicts, and publication
metadata.

Target public guarantees:

- stable GitHub Pages report URLs;
- complete report Markdown and static pages;
- machine-readable `sources.yaml`, `claims.jsonl`, `manifest.json`, `publication.json`, and `qa.json` where applicable;
- legacy reports marked clearly as `legacy-aggregate`;
- no private local paths, machine identifiers, raw user-generated content, internal dispatch logs, or runtime state blobs.

## Layout

```text
docs/                       Public policy and operating docs
reports/YYYY/MM/DD/         One self-contained report directory per date
schemas/                    JSON Schema contracts
templates/                  Authoring templates
.github/ISSUE_TEMPLATE/     Managed project-control issue templates
tmp/                        Ignored local bootstrap staging
```

No Python scripts are tracked in this repository.

## Reader Boundary

Reports are market commentary and source-backed analysis, not financial advice. Questions and corrections are handled through the associated public publication channel and recorded here only as sanitized Q&A metadata.
