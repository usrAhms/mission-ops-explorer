# MissionOps Explorer — Procurement Intelligence Demo

An interactive front-end dashboard exploring **synthetic procurement invoice data**. It demonstrates how an analyst can turn operational records into a review queue, spending summaries, and simple explainable flags.

**[Open the live demo](https://YOUR_GITHUB_USERNAME.github.io/mission-ops-explorer/)** (replace username after publishing)

## Features
- 72 deterministic, fabricated invoices for demonstration
- Filter by agency, review priority, or keyword
- Monthly spending visualization and vendor concentration ranking
- Explainable review priorities and duplicate candidates
- Export current filtered records as CSV
- Fully responsive; no dependencies, build steps, or API keys

## Run locally
Download this repo and open `index.html` in a web browser.

## Review priority logic
- **High:** Same vendor/date/amount as another record, or invoice >= $90,000
- **Medium:** Invoice >= $45,000
- **Low:** Remaining records

This is **rules-based prioritization**, not AI, fraud detection, predictive analytics, or a validated compliance tool. Duplicate matches and high amounts do not prove errors or misconduct. Thresholds are arbitrary for learning purposes.

## Technical choices
Vanilla HTML, CSS, JavaScript, deterministic synthetic-data generation, browser-side aggregation and CSV export. No uploads, storage, personal data, network calls, or external libraries.

## Scope and attribution
Independent student portfolio prototype created in November 2026. All agencies, vendors and invoice records are fictional. Not connected to Inalab, its tools or clients, or the U.S. government. Inspired generally by public discussions of procurement data quality and decision-support workflows. Do not use for real procurement decisions.

## Possible next steps
- Load user-supplied CSV files with validation and error handling
- Add a documented API backend and automated tests
- Compare records against source evidence with human approval
- Add user access control and a full audit trail before handling actual data
