# FSOS Roadmap

## Document Status

- **Status:** Living Document
- **Verified Version:** v1.0.34
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
8. Engineer-controlled recommendations before autonomous action.

## Phase 1 — Foundation

**Status: Verified Green**

- Repository standards
- Engineering-OS governance
- Cloudflare Workers deployment
- D1 persistence
- Synchronization foundation
- Runtime/deployment verification
- Controlled legacy architecture cleanup

## Phase 2 — Core Platform

**Status: Active**

- Dashboard
- Mission Control
- Machine Passport
- Smart MHC
- MHC History
- Planner
- Contract Management
- Recommended Parts Master

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
- Diagnose and correct the saved Temperature Inspection chart defect.

## Phase 4 — Unified Report Engine

**Status: Planned — after Phase 3 data foundation**

Target outputs:

1. **Full PDF** — complete engineering/customer report with structured sections, evidence, comparison, findings, actions, and buyoff.
2. **Compact PDF** — one-page executive/customer summary.
3. **PPTX** — presentation-ready engineering summary.

Report architecture principles:
- Legacy Excel = engineering coverage baseline.
- Structured MHC record = report data source.
- Visual design = optimized for customer understanding.
- Each data type gets an appropriate visual representation.
- Previous vs Current comparison is explicit and traceable.
- Evidence is preserved.
- Report generation is deterministic and not dependent on manually recreating engineering values.

## Phase 5 — MHC Recommendation Intelligence

**Status: Planned**

### Current-condition recommendations

MHC Autopilot should be able to:
- inspect current MHC findings;
- suggest matching parts from the Recommended Parts Master;
- provide the engineering reason for each suggestion;
- allow the engineer to accept, reject, or manually select another part.

Rules:
- Never invent a part.
- Never bypass engineer control.
- Suggestions must resolve to authoritative catalog records.

### Predictive-maintenance recommendations

**Status: Future**

Potential inputs:
- laser operating hours;
- MHC history;
- measurement drift;
- temperature history;
- beam profile history;
- previous replacements;
- recommended lifespan;
- service history.

The output should be a conservative attention/risk recommendation, not an unsupported exact failure prediction.

## Phase 6 — Offline Capability

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

## Phase 7 — Desktop Platform

**Status: Future — not current scope**

- Standalone desktop application
- Local storage
- Native OS integration
- Improved offline capability

Potential technologies:
- Tauri
- Electron evaluation
- SQLite

## Current Priority

**Stabilize the saved Temperature Inspection record visualization, review the actual full MHC report evidence, then design current-condition MHC Autopilot → Recommended Parts recommendations.**

Predictive maintenance remains parked until the above foundation is stable.

## Release Philosophy

Each release should provide measurable improvement in reliability, usability, maintainability, performance, or engineering efficiency.

## Revision Policy

Update this roadmap when a milestone or major architectural direction changes. Keep sprint-level tasks elsewhere.
