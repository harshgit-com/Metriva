# Metriva

Metriva is a responsive analytics workspace prototype that turns data into understandable dashboards.

## Run locally

Open `index.html` in a modern browser. No build step or package installation is required.

## Prototype features

- Responsive workspace layout with Overview, My dashboards, Data hub, Analyst, Reports and Settings.
- Sample KPI cards, revenue trend, category breakdown and transaction table.
- Local CSV import, basic CSV parsing, column preview and row counts.
- Demo analyst responses for the included sample dataset.
- Mobile navigation and responsive layouts.

## Important limitations

This is a front-end prototype, not a production SaaS application. CSV files are read locally in the browser and are not uploaded or persisted. The analyst uses illustrative responses; it is not connected to an AI model or a verified data query engine.

Production work still required:
- Authentication and workspace membership.
- Secure backend storage and saved dashboards.
- Robust Excel/CSV ingestion, validation, joins and deterministic metric calculations.
- AI recommendations and conversational dashboard editing.
- Google Sheets and other live data connectors.
- Sharing permissions, exports, audit logs and billing.
- Server-side authorization, privacy controls, tests and deployment configuration.

## Deploy with GitHub Pages

In the repository settings, open **Pages**, choose **Deploy from a branch**, select **main** and **/(root)**, then save. GitHub Pages will publish the root `index.html` after its deployment finishes.
