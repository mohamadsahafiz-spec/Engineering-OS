# FSOS Roadmap

## Document Status

- **Status:** Living Document
- **Verified Version:** v1.0.14
- **Owner:** Atlas

## Product Vision

Build a premium engineering operations platform that enables field engineers to execute work, manage machine data, generate professional reports, and synchronize information reliably across devices.

## Development Priorities

1. Stability before expansion.
2. Foundations before features.
3. Verified reliability before optimization.
4. Documentation alongside implementation.
5. Free-first infrastructure unless a paid dependency is explicitly justified and approved.

## Phase 1 — Foundation

**Status: Verified Green**

- Repository standards
- Engineering-OS governance
- Cloudflare Workers deployment
- D1 persistence
- Synchronization foundation
- Runtime/deployment verification

## Phase 2 — Core Platform

**Status: Active Development**

- Dashboard
- Mission Control
- Machine Passport
- Machine Health Check
- Planner
- Report Studio
- Contract Management

## Phase 3 — Operational Excellence

**Status: Planned**

- Workflow optimization
- Report improvements
- Search
- Performance improvements
- Engineering analytics

## Phase 4 — Offline Capability

**Status: Future**

- Local database
- Offline mode
- Automatic synchronization
- Conflict resolution
- Recovery mechanisms

Potential technologies:

- SQLite
- Sync Engine
- Cloudflare Workers
- D1

## Phase 5 — Desktop Platform

**Status: Future — not current scope**

- Standalone desktop application
- Local storage
- Native OS integration
- Improved offline capability

Potential technologies:

- Tauri
- Electron evaluation
- SQLite

The web → standalone transition must preserve the existing Worker/D1 synchronization architecture wherever practical.

## Phase 6 — Intelligence

**Status: Future**

- Predictive maintenance
- Engineering insights
- Operational dashboards
- AI-assisted reporting
- Smart recommendations

## Current Priority

**Resolve durable image persistence without introducing an unapproved recurring storage cost.**

Current image evidence is browser-local. The next architecture decision must compare genuinely free/no-billing options before activating R2 or another paid-capable service.

## Release Philosophy

Each release should provide measurable improvement in reliability, usability, maintainability, performance, or engineering efficiency.

## Revision Policy

Update this roadmap when a milestone or major architectural direction changes. Keep sprint-level tasks elsewhere.
