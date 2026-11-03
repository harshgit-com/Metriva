# Metriva

Metriva is a dataset-first analytics workspace prototype. Its core flow is **connect a spreadsheet → inspect its real fields → generate relevant summaries and charts → filter the records → ask questions about the data → save a report configuration**.

## Run it

Open `index.html` in a modern browser. There is no build step or package installation.

## Included in this version

- New responsive Metriva interface with a custom SVG brand mark, desktop sidebar, mobile navigation, top search bar, and light/dark appearance.
- CSV import with quoted-cell parsing and drag-and-drop.
- Excel `.xlsx` / `.xls` import through SheetJS loaded on demand from jsDelivr; the first worksheet is used.
- Dataset profiling based on actual imported values: numeric, date, category, text and empty fields.
- Expanded dataset-aware KPI cards. General datasets include numeric totals and averages, unique category counts, completeness and duplicate-row counts. Event datasets additionally detect event names/types, user IDs, session IDs, timestamps, pages/screens, devices and browsers to calculate event volume, unique users, unique sessions, event types, events per user/session and active dates.
- Multiple charts generated from the detected schema rather than a fixed demo: chronological event/activity timelines, event-type rankings, top pages/screens, device and browser mix, category distributions, numeric comparisons and date trends. Charts recalculate with dashboard filters.
- Event-aware written insights covering audience, session behaviour, most visited pages, activity types, date coverage, data quality and duplicates.
- Dashboard filter that recalculates the metrics, charts, insights and record preview for the selected dimension value.
- Computed analysis for numeric totals/averages/ranges, common categories, missing values and date coverage.
- Data Analyst page with built-in deterministic calculations plus an optional browser-hosted open-source Metriva AI model (WebLLM/Qwen 2.5 0.5B) for natural-language dataset questions. The model runs in the user's browser after a one-time model download; dataset context is passed locally to the model.
- Saved report configurations in browser local storage.
- Responsive layouts for desktop, tablet and mobile.

## Important limitations

This remains a **front-end prototype**, not a production SaaS. Metriva AI currently uses a small open-source model loaded in the browser through WebLLM and WebGPU. It requires a compatible browser/device and an internet connection for the initial model download. Model performance is limited by the user's hardware; if WebGPU or model loading is unavailable, built-in deterministic calculations remain available. It is not yet a hosted multi-user AI service, and the AI currently provides analysis and dashboard recommendations rather than directly applying dashboard edits.

There is no authentication, cloud database, cross-device sync, team collaboration, live source connectors, sharing permissions, billing or production audit log. The current dataset remains in browser memory for the active session. Saved reports store configuration/metadata, not a copy of the uploaded file; re-import the same file to restore its data. Clearing browser storage can remove saved reports. Excel import needs an internet connection to load SheetJS.

No end-to-end browser test or production deployment has been completed yet. Keep original copies of important data.

## Suggested next engineering milestones

1. Add automated browser tests for CSV/XLSX upload, filters, charts, saved reports and mobile navigation.
2. Add secure accounts, backend storage and dataset versioning.
3. Expand Metriva AI with validated dashboard-edit actions, more capable open models, and an optional self-hosted inference service when hosting and GPU resources are available.
4. Add connectors, sharing permissions, collaboration and audit logs.

## Static deployment

For a static preview, use GitHub Pages: repository **Settings → Pages → Deploy from a branch → main → /(root)**. This hosts the front-end only; it does not add backend or AI capabilities.
