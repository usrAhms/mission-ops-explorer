# MissionOps Explorer — Procurement Intelligence Demo

An interactive front-end dashboard exploring **synthetic procurement invoice data**. It demonstrates how an analyst can turn operational records into a review queue, spending summaries, and simple explainable flags.

**[Open the live demo](https://usrAhms.github.io/mission-ops-explorer/)** (replace username after publishing)

## Features
- 72 deterministic, fabricated invoices for demonstration
- Filter by agency, review priority, or keyword
- Monthly spending visualization and vendor concentration ranking
- Explainable review priorities and duplicate candidates
- Export current filtered records as CSV
- Import your own CSV (required headers: `id,agency,vendor,date,amount`) with client-side validation
- Open each invoice, assign review status, add a reviewer name and case notes
- Save review decisions to browser localStorage and export the audit-ready review worksheet
- Restore the synthetic sample dataset
- Fully responsive; no dependencies, build steps, or API keys

## Run locally
Download this repo and open `index.html` in a web browser.

## Review priority logic
- **High:** Same vendor/date/amount as another record, or invoice >= $90,000
- **Medium:** Invoice >= $45,000
- **Low:** Remaining records

This is **rules-based prioritization**, not AI, fraud detection, predictive analytics, or a validated compliance tool. Duplicate matches and high amounts do not prove errors or misconduct. Thresholds are arbitrary for learning purposes.

## Technical choices
Vanilla HTML, CSS, JavaScript, deterministic synthetic-data generation, browser-side aggregation and CSV export. No external libraries or network calls. Review notes are saved in the current browser via localStorage. Imported CSV files are processed on-device, not uploaded. Do not enter confidential or real client data into this demonstration.

## Scope and attribution
Independent student portfolio prototype created in November 2026. All agencies, vendors and invoice records are fictional. Not connected to Inalab, its tools or clients, or the U.S. government. Inspired generally by public discussions of procurement data quality and decision-support workflows. Do not use for real procurement decisions.

## Possible next steps
- Load user-supplied CSV files with validation and error handling
- Add a documented API backend and automated tests
- Compare records against source evidence with human approval
- Add user access control and a full audit trail before handling actual data

## Example CSV schema

```csv
id,agency,vendor,date,amount
INV-2001,Agency East,Example Vendor,2026-05-14,45000
INV-2002,Agency East,Example Vendor,2026-05-14,45000
```

Use fictional records. Invoice IDs must be unique. Date format is YYYY-MM-DD. The imported file supports up to 5,000 records / 2 MB. Review notes are browser-local and are not synchronized.

## What I would improve in production

Authentication, role-based permissions, server-side audit logs, secure data retention, testing with verified datasets, and procurement-specific risk validation would be needed before any operational use.
