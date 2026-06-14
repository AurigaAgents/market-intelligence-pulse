# GitHub Pages

Pages are rendered locally and served from committed static files. GitHub Actions and repo-local render scripts are out of scope for the initial implementation.

Requirements:

- root and per-date pages are `index.html`;
- `.nojekyll` is present at the publishing-source root;
- pages link to downloadable report artifacts where present;
- legacy pages display a `legacy-aggregate` provenance warning;
- new pages display source and claim coverage counts;
- publication waits until the deployed Pages URL returns HTTP 200.

`index.md` is not a public repository artifact. Markdown page sources, if any, stay local to the renderer or template system.
