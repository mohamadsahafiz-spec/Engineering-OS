# FSOS Architecture

## System Status

- **Status:** Active Development
- **Verified Version:** v1.0.14
- **Architecture Owner:** Atlas

## Purpose

This document is the architectural source of truth for FSOS structure and responsibility boundaries.

## Design Principles

- Durable server-side source of truth for operational records
- Reliable multi-device synchronization
- Offline capability where practical
- Modular workspaces
- Predictable workflows
- Minimal coupling
- Future desktop portability

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
       Durable structured operational data

Image Evidence (current)
        │
        └── Browser IndexedDB only  ← pending replacement

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

### Machine Health Check
Inspection workflow, parameter recording, before/after comparison, measurements, and image evidence.

### Report Studio
Executive/customer/engineering report generation and export.

### Contract Management
Contract overview, SLA tracking, quarterly schedule, and customer commitments.

### Planner
Engineering schedule, mission planning, calendar, and resources.

### Sync Engine
Device synchronization, queued changes, conflict handling, offline recovery, and reconciliation.

## Data Ownership

| Data | Authoritative Location |
|---|---|
| Operational records | D1 |
| Sync state/queue | Client + Worker/D1 synchronization flow |
| Current image payloads | Browser IndexedDB (temporary limitation) |
| Future image payloads | To be selected after free-first evaluation |
| Desktop local data | Future SQLite |

## Architectural Rules

- Do not use Worker memory as durable state.
- Do not store binary image payloads in D1 unless explicitly justified.
- Do not introduce R2 or another paid-capable storage service without Founder approval.
- Keep UI, API, persistence, and sync responsibilities separated.
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
