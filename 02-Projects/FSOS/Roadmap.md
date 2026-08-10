# FSOS Roadmap

## Document Status

- **Status:** Living Document
- **Verified Version:** v1.0.16
- **Owner:** Atlas

## Product Vision

Build a premium engineering operations platform that enables field engineers to execute work, manage machine data, generate professional customer reports, and synchronize information reliably across devices.

The report experience should evolve the legacy Excel standard into clear, visual engineering communication rather than reproducing spreadsheet presentation.

## Development Priorities

1. Stability before expansion.
2. Foundations before features.
3. Verified reliability before optimization.
4. Documentation alongside implementation.
5. Free-first infrastructure unless a paid dependency is explicitly justified and approved.
6. Preserve proven engines before attempting future enhancement.
7. Capture authoritative structured engineering data before automating report rendering.

## Phase 1 — Foundation

**Status: Verified Green**

- Repository standards
- Engineering-OS governance
- Cloudflare Workers deployment
- D1 persistence
- Synchronization foundation
- Runtime/deployment verification
- v1.0.15 large telemetry quota optimization and IndexedDB raw telemetry storage
- v1.0.16 controlled legacy architecture cleanup

## Phase 2 — Core Platform

**Status: Active**

- Dashboard
- Mission Control
- Machine Passport
- Smart MHC
- MHC History
- Planner
- Contract Management

Obsolete 01–08 MHC stage workflow and Executive Reports have been removed.

## Phase 3 — Smart MHC Engineering Record

**Status: Current Priority**

- Establish Smart MHC as the authoritative MHC record.
- Preserve existing stable calculation engines.
- Integrate the proven Laser Hour Monitor.
- Integrate the proven Temperature Engine without redesign.
- Capture Focus Optimization result and evidence.
- Capture Power Offset result.
- Capture Stage & Scanner Calibration / AGC result and evidence.
- Preserve Laser Profile as customer/product/process context.
- Capture Product Via Quality: diameter, roundness, taper, and images.
- Establish explicit Previous vs Current baseline selection.
- Ensure Canvas presentation cannot silently diverge from authoritative engineering data.

## Phase 4 — Unified Report Engine

**Status: Planned — after Phase 3 data foundation**

Target outputs:

1. **Full PDF** — complete engineering/customer report with structured sections, evidence, comparison, findings, actions, and buyoff.
2. **Compact PDF** — one-page executive/customer summary; page size may be adapted when necessary to preserve readability.
3. **PPTX** — presentation-ready engineering summary.

Report architecture principles:

- Legacy Excel = engineering coverage baseline.
- Structured MHC record = report data source.
- Visual design = optimized for customer understanding.
- Each data type gets an appropriate visual representation.
- Previous vs Current comparison is explicit and traceable.
- Evidence is preserved.
- Report generation is deterministic and not dependent on manually recreating engineering values.

Potential report flow:

```text
Cover
  ↓
Index
  ↓
Machine / Service Context
  ↓
Executive Health Summary
  ↓
Laser Hours
  ↓
Laser Power — Previous / Current / Comparison
  ↓
Beam Profile — Previous / Current / Comparison
  ↓
Focus Optimization
  ↓
Power Offset
  ↓
Product / Laser Profile
  ↓
Product Via Quality
  ↓
Stage & Scanner Calibration / AGC
  ↓
Temperature
  ↓
Spare Recommendations
  ↓
Findings / Corrective Actions
  ↓
Evidence
  ↓
Buyoff
```

The final order may be improved during report UX/design work.

## Phase 5 — Offline Capability

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

## Phase 6 — Desktop Platform

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

## Phase 7 — Intelligence

**Status: Future**

- Predictive maintenance
- Engineering insights
- Operational dashboards
- AI-assisted reporting
- Smart recommendations

## Current Priority

**Build the Smart MHC authoritative data foundation and report readiness without destabilizing proven engines.**

Durable image persistence remains unresolved and deferred under free-first governance. R2 is not activated.

## Release Philosophy

Each release should provide measurable improvement in reliability, usability, maintainability, performance, or engineering efficiency.

## Revision Policy

Update this roadmap when a milestone or major architectural direction changes. Keep sprint-level tasks elsewhere.
