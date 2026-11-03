# Metriva

Metriva is a dataset-first analytics and dashboard-building MVP. The product flow is: upload a spreadsheet → inspect its schema → accept or edit suggested KPIs and charts → filter and configure the dashboard → ask questions about the data → save a dashboard.

## Run it

Open `index.html` in a modern browser. No build step or package installation is required.

## Current working prototype features

- CSV import with quoted-cell parsing; Excel `.xlsx` and `.xls` import via SheetJS loaded on demand from jsDelivr.
- No pre-filled business dataset or fabricated metrics. A blank workspace is shown until the user imports data.
- Column inference based on uploaded values: numeric, date, category and text.
- Suggested metrics and visualisations are selected from detected columns, not hard-coded field names.
- Editable KPI cards with Sum, Average, Count, Minimum and Maximum calculations.
- Editable bar, line, area, donut and table visualisations with configurable dimension, measure and aggregation.
- A dashboard-level dimension filter that updates KPI cards, charts and underlying records together.
- Dataset preview and data profile.\n- Computed insight panel covering numeric summaries, dominant categories, missing-value completeness and date coverage for the active filtered records.
- Prompt interface with a local command interpreter for supported questions and dashboard actions (summaries, missing values, totals, averages, top categories, adding charts/metrics and date trends).
- Save and reopen dashboard snapshots in browser local storage.
- Responsive layout and light/dark appearance.

## Important limitations

This is still a client-side MVP, not a production SaaS. The prompt interface is a deterministic local command interpreter, **not a connected generative AI model**. It supports a limited set of intents and should not be presented as general AI reasoning. A production AI copilot needs a secure backend and model-provider integration; API keys must never be placed in browser code.

There is no authentication, cloud database, cross-device sync, team workspace, live data connector, server-side permissions, billing, or production audit log. Dashboard snapshots are stored in the current browser and may be lost if browser storage is cleared. Imported files are processed locally. Excel support requires the SheetJS CDN to load. Only the first worksheet is imported. Very large files may exceed browser storage or browser memory.

Do not use this prototype as the only copy of important business data. Keep the original spreadsheet and export backups.

## Production roadmap

1. Add authentication, secure workspaces and per-user authorization.
2. Add database and object storage with reliable dataset versioning.
3. Move file parsing and large-scale analytics to a secure backend.
4. Connect a real AI copilot through a server-side provider integration with schema-aware tool calling and grounded responses.
5. Add connectors, collaboration, dashboard sharing, audit logs, billing and automated tests.

## Deploy with GitHub Pages

In repository Settings → Pages, select **Deploy from a branch**, choose **main** and **/(root)**, then save. GitHub Pages can host this static prototype, but it cannot provide the secure backend capabilities listed above.
