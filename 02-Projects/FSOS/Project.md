# FSOS (Field Service Operations System)

## Project Status

- **Status:** Active Development
- **Verified Version:** v1.0.34
- **Foundation:** Green / verified
- **Priority:** Smart MHC and customer-facing report engineering
- **Owner:** Sahafiz
- **Lead Architect:** Atlas
- **Implementation Engineer:** Mikasa

## Purpose

FSOS is an engineering operations platform for field service execution, Machine Health Checks, machine data, reporting, contract management, and operational intelligence.

## Vision

Build a reliable engineering operating platform that captures the engineering record once, preserves traceability, and turns it into useful operational and customer-facing information without forcing engineers or customers to work from legacy spreadsheet-style presentation.

## Verified Technology Stack

### Frontend

- React
- Vite
- Tailwind
- Cloudflare Worker static assets / frontend delivery

### Backend

- Cloudflare Workers

### Database

- Cloudflare D1

### Version Control

- Git
- GitHub

### Future / Not Yet Active

- R2 for durable image storage; not activated
- SQLite for future desktop/offline architecture
- Tauri or Electron evaluation for future standalone software

## v1.0.34 Verified Additions

### Recommended Parts Master

Verified stable:
- Full CRUD
- Zero-state lifecycle
- CSV/JSON structured import
- Validation preview and explicit confirmation
- Composite duplicate detection using `machineFamily + partNumber`
- Strict BMD302W / BMD250WM family isolation
- Search, category and criticality filtering
- Interactive column sorting and presets
- Duration/lifespan parsing
- Manual Add/Edit/Delete after import
- Authoritative persistence
- No ghost records

The Recommended Parts Master is the authoritative catalog for parts that may be manually selected or later referenced by MHC recommendation logic.

### Customer Identity Reconciliation

Imported machines are reconciled into authoritative persistent Customer records with stable `customerId` values.

Customer rename cascades to associated machines.

Synthetic customer resurrection paths were removed.

Verified:
- single authoritative customer per imported identity;
- stable customer links;
- rename persistence across reload;
- no duplicate/ghost customers.

## Current Runtime Issue

Saved Temperature Inspection records currently show a malformed time-series visualization in the deployed runtime:

- time axis/tooltip can display `NaN`;
- the chart may collapse instead of rendering the expected time-series;
- the record still reports substantial raw data.

This must be diagnosed through persistence → reload → aggregation/bucketing → chart-data transformation → renderer before the next report milestone.

Do not assume the root cause without evidence.

## Smart MHC — Current Primary Workspace

Smart MHC is the primary MHC workspace and the foundation for the future unified report engine.

The intended architectural direction is:

```text
Structured MHC Record
        ↓
Authoritative engineering data
        ├── Smart MHC presentation
        ├── MHC History
        └── Future Report Engine
              ├── Full PDF
              ├── Compact PDF
              └── PPTX
```

Canvas/widget layout is presentation. It must not become a competing source of truth for engineering values.

## MHC Recommendation Direction

### Current-condition recommendation — planned

MHC Autopilot may analyze current inspection findings such as Laser Power, Beam Profile, Temperature, Product/Process and related engineering results.

It may suggest a part only by resolving to an existing record in the authoritative Recommended Parts Master.

Engineer control remains mandatory:
- accept an Autopilot suggestion;
- reject it;
- or manually search/select a different part.

Autopilot must not invent catalog parts.

### Predictive-maintenance recommendation — future

Predictive maintenance is intentionally later scope.

Future recommendations may use accumulated:
- laser operating hours;
- MHC history;
- measurement drift;
- temperature history;
- beam profile history;
- previous replacements;
- recommended lifespan;
- service history.

The system should provide conservative risk/attention recommendations rather than unsupported exact failure predictions.

## MHC Report Evolution

The legacy customer Excel report is the engineering baseline for coverage and traceability, not the visual destination.

FSOS should evolve the report by:
- reorganizing information around customer understanding;
- automating calculations and comparisons;
- using visualizations appropriate to each data type;
- preserving evidence and traceability;
- clearly separating current condition, previous baseline, findings, actions, and recommendations.

The report should make it easy to understand:

**What was checked → what changed → whether it is within specification → what was found → what was done → what evidence supports the result → what should happen next.**

## Requirement Verification Rule

Do not invent engineering report requirements from an audit interpretation.

The hierarchy is:

1. Actual customer workflow and engineering practice
2. Actual customer report/reference evidence
3. Verified FSOS implementation evidence
4. Engineering analysis and recommendation

If a requirement is not verified, label it as unverified and request evidence before changing the data model.

## Long-Term Architecture Direction

FSOS may evolve from a browser-first application into standalone desktop software.

Future direction:

**Standalone Client → Local Database → Sync Engine → Cloudflare Worker → D1**

This is future scope, not current implementation work.

## Engineering Principles

FSOS follows Engineering-OS Core governance. Project decisions must respect evidence discipline, cost constraints, change control, and verification requirements.

## Revision Policy

Update this document when verified project architecture, status, or major decisions change. Do not use it as a sprint backlog.
