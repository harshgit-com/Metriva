# Metriva

Metriva is a browser-based analytics workspace MVP. It turns spreadsheet rows into calculated summaries, charts and saved dashboard snapshots.

## Run it

Open `index.html` in a modern browser. There is no build step or package installation.

## Working in-browser features

- Responsive workspace with Overview, My dashboards, Data hub, Analyst, Reports and Settings.
- Import CSV files directly in the browser, including quoted cells and comma-containing values.
- Import Excel `.xlsx` and `.xls` files using SheetJS loaded on demand from jsDelivr. An internet connection is needed the first time Excel support loads.
- Automatic detection of numeric, date-like and category columns.
- KPI calculations, numeric trend chart, category breakdown, top-value bars and recent-row preview based on the active dataset.
- Rule-based analyst questions calculated from the actual imported rows: totals, averages, row counts, top categories, missing values, columns and date trends.
- Save and reopen dashboard snapshots in browser local storage.
- Export the active dataset as CSV and print/save the dashboard view as PDF.
- Light/dark appearance and responsive mobile navigation.
- File processing happens in the browser; imported data is not uploaded to a Metriva server.

## Current limitations — not production SaaS yet

This is a client-side MVP, not a multi-user production service. It has no user authentication, cloud database, cross-device sync, team workspaces, server-side authorization, live connectors, billing or real generative-AI integration. The Analyst is deterministic and rule-based; it does not use an LLM. Dashboard snapshots and imported data are stored only in the current browser and can be lost if browser storage is cleared. Large datasets may exceed browser storage limits. Excel import requires the external SheetJS CDN to be reachable.

Do not store sensitive or business-critical data here as the only copy. Export and keep a backup.

## Recommended production milestones

1. Add authentication and secure workspace membership.
2. Add a backend database and object storage with per-user access rules.
3. Move ingestion and large-file processing to a validated backend pipeline.
4. Add a server-side AI provider integration with secrets kept off the client.
5. Add real connectors, sharing permissions, audit logs, billing and automated tests.

## Deploy with GitHub Pages

In repository Settings → Pages, choose **Deploy from a branch**, select **main** and **/(root)**, then save. GitHub Pages publishes the root `index.html` after the deployment finishes. GitHub Pages can host this static MVP, but it cannot provide the secure backend services listed above.
