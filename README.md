# Metriva

Metriva is a dataset-first analytics workspace prototype. Its core flow is **connect a spreadsheet → inspect its real fields → generate relevant summaries and charts → filter the records → ask questions about the data → save a report configuration**.

## Run it

Open `index.html` in a modern browser. There is no build step or package installation.

## Included in this version

- New responsive Metriva interface with a custom SVG brand mark, desktop sidebar, mobile navigation, top search bar, and light/dark appearance.
- CSV import with quoted-cell parsing and drag-and-drop.
- Excel `.xlsx` / `.xls` import through SheetJS loaded on demand from jsDelivr; the first worksheet is used.
- Dataset profiling based on actual imported values: numeric, date, category, text and empty fields.
- Dashboard KPI cards derived from the uploaded dataset: record count, semantic numeric total when a suitable column exists, numeric average, and missing-cell count.
- Charts generated from detected fields: time series when a date and numeric field exist, category comparison when suitable dimensions exist, or a record-count breakdown otherwise.
- Dashboard filter that recalculates the metrics, charts, insights and record preview for the selected dimension value.
- Computed analysis for numeric totals/averages/ranges, common categories, missing values and date coverage.
- Data Analyst page with a local deterministic query helper for summaries, missing values, numeric statistics, record counts and category rankings.
- Saved report configurations in browser local storage.
- Responsive layouts for desktop, tablet and mobile.

## Important limitations

This is a **front-end prototype**, not a production SaaS. The Data Analyst helper is rule-based local code, **not a real generative AI model**. It supports a limited set of question patterns and does not provide open-ended reasoning. A real AI analyst requires a secure server-side model integration; API keys must never be embedded in browser JavaScript.

There is no authentication, cloud database, cross-device sync, team collaboration, live source connectors, sharing permissions, billing or production audit log. The current dataset remains in browser memory for the active session. Saved reports store configuration/metadata, not a copy of the uploaded file; re-import the same file to restore its data. Clearing browser storage can remove saved reports. Excel import needs an internet connection to load SheetJS.

No end-to-end browser test or production deployment has been completed yet. Keep original copies of important data.

## Suggested next engineering milestones

1. Add automated browser tests for CSV/XLSX upload, filters, charts, saved reports and mobile navigation.
2. Add secure accounts, backend storage and dataset versioning.
3. Add a real AI analyst through a server-side integration with schema-aware tools and grounded answers.
4. Add connectors, sharing permissions, collaboration and audit logs.

## Static deployment

For a static preview, use GitHub Pages: repository **Settings → Pages → Deploy from a branch → main → /(root)**. This hosts the front-end only; it does not add backend or AI capabilities.
