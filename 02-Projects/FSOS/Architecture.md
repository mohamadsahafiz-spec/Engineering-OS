# FSOS Architecture

## System Status

- **Status:** Active Development
- **Verified Version:** v1.0.16
- **Architecture Owner:** Atlas

## Purpose

This document is the architectural source of truth for FSOS structure and responsibility boundaries.

## Design Principles

- Durable server-side source of truth for structured operational records
- Reliable multi-device synchronization
- Offline capability where practical
- Modular workspaces
- Predictable workflows
- Minimal coupling
- Future desktop portability
- Structured engineering data separated from presentation
- Proven engineering engines preserved before future enhancement
- Customer-facing reporting optimized for understanding, not spreadsheet reproduction

## High-Level Architecture

```text
                         User
                          │
                   React + Vite UI
                          │
             Cloudflare Worker Runtime
                          │
                 API / Sync / Logic
                          │
                     Cloudflare D1
                          │
              Authoritative structured data
                          │
             ┌────────────┼─────────────┐
             ↓            ↓             ↓
         Smart MHC     MHC History   Report Engine
        presentation   & records       future
                                       │
                          ┌────────────┼────────────┐
                          ↓            ↓            ↓
                       Full PDF   Compact PDF     PPTX

Image Evidence (current)
        │
        └── Browser IndexedDB only  ← pending durable cross-device solution

Future Image Architecture
        │
        └── Approved object storage / free alternative

Future Desktop
        │
        └── Tauri or Electron
                │
             SQLite
                │
           Sync Engine
                │
        Cloudflare Worker
                │
                D1
```

## Production Deployment

FSOS production target is **Cloudflare Workers**, not Pages.

Deployment chain:

**GitHub → Cloudflare Worker build/deployment → Worker runtime → workers.dev**

Cloudflare Pages may be used by other projects, but it is not the FSOS production deployment path.

## Core Modules

### Dashboard
Daily overview, mission summary, upcoming work, and notifications.

### Mission Control
Active work execution, workflow progression, and SOP guidance.

### Machine Passport
Machine information, specifications, service history, components, and laser information.

### Smart MHC
Primary MHC workspace for structured inspection data, engineering evidence, calculations, historical comparison, and customer-report preparation.

### MHC History
Historical MHC sessions and access to prior Smart MHC workspaces. It is important to future Previous vs Current reporting.

### Contract Management
Contract overview, SLA tracking, quarterly schedule, and customer commitments.

### Planner
Engineering schedule, mission planning, calendar, and resources.

### Sync Engine
Device synchronization, queued changes, conflict handling, offline recovery, and reconciliation.

### Future Report Engine
A unified renderer consuming authoritative MHC data to produce:
- Full PDF
- Compact one-page PDF
- PPTX

The renderer must not require manual recreation of engineering values inside a separate report database.

## Smart MHC Data Authority

The intended direction is:

```text
MHCSession / authoritative structured record
                    │
                    ├── Smart MHC UI
                    ├── MHC History
                    └── Report Engine
```

Canvas widgets are presentation/projection state. They must not become an independent source of engineering truth.

Future implementation must ensure that editable engineering values do not silently diverge between canvas widget data and the authoritative MHC record.

## Report Architecture Principles

The legacy Excel report remains the engineering coverage baseline, not the final visual design.

Report generation should be deterministic and structured:

**Engineering data → calculations → comparison → interpretation → evidence → visual renderer → output**

Visuals should be selected according to data meaning. Examples include:
- specification bands for values with limits;
- Previous/Current delta visuals for comparable measurements;
- profile image comparison/overlay for beam data;
- optimization curves for focus data;
- adjustment scales for power offsets;
- time-series operating-band charts for temperature;
- quality/evidence panels for product via inspection;
- result-vs-specification panels for calibration;
- action cards for spare recommendations;
- finding → action → result flows for corrective actions.

These are design directions, not permission to fabricate data or conclusions.

## Proven External Engines

### Temperature

The temperature engine is a proven external engine and must be treated as stable during the current Smart MHC report phase. Integrate/migrate it; do not redesign it unless a verified defect requires intervention.

### Laser Hours

The Laser Hour Monitor is a proven external engine and should be integrated into FSOS and the customer report. Do not redesign it during the current Smart MHC report phase.

Future enhancement of either engine is a separate decision and sprint.

## Data Ownership

| Data | Authoritative Location |
|---|---|
| Operational records | D1 |
| Smart MHC structured records | MHC session / D1-backed FSOS persistence |
| Historical MHC sessions | MHC History / authoritative MHC records |
| Sync state/queue | Client + Worker/D1 synchronization flow |
| Current image payloads | Browser IndexedDB (temporary limitation) |
| Future image payloads | To be selected after free-first evaluation |
| Desktop local data | Future SQLite |

## Architectural Rules

- Do not use Worker memory as durable state.
- Do not store binary image payloads in D1 unless explicitly justified.
- Do not introduce R2 or another paid-capable storage service without Founder approval.
- Keep UI, API, persistence, and sync responsibilities separated.
- Do not let Canvas presentation state become a competing engineering data store.
- Do not redesign proven external engines during unrelated report work.
- Major architectural changes require an explicit decision record.

## Future Desktop Architecture

```text
Standalone Desktop Client
        ↓
Local SQLite
        ↓
Sync Engine
        ↓
Cloudflare Worker
        ↓
D1
```

The desktop migration is a future evolution and must not destabilize the current web deployment.
