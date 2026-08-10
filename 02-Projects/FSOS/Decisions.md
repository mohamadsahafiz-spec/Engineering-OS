# FSOS Engineering Decisions

## Document Status

- **Status:** Living Document
- **Verified Version:** v1.0.16
- **Owner:** Atlas

## Decision Record Format

Every major decision should include:

- Decision
- Reason/evidence
- Alternatives considered
- Cost/operational impact
- Reversibility
- Date/version
- Status

## Decision 001 — Cloudflare Platform

**Decision:** Cloudflare is the primary FSOS deployment ecosystem.

**Reason:** Workers and D1 provide the verified production runtime and relational persistence with low operational overhead.

**Important boundary:** R2 and other paid-capable services are not automatically included merely because they are in the Cloudflare ecosystem.

**Status:** Approved

## Decision 002 — React Frontend

React is the standard FSOS frontend framework.

**Status:** Approved

## Decision 003 — D1 Authoritative Record Storage

D1 is the authoritative server-side source of truth for structured FSOS records.

**Reason:** The previous Worker memory store was volatile. D1 persistence and synchronization are now verified.

**Status:** Approved

## Decision 004 — Workers Production Runtime

FSOS production uses Cloudflare Workers. Pages is not the production backend/deployment target.

**Reason:** Pages and Workers are separate deployment pipelines; confusing them previously caused investigation drift.

**Status:** Approved

## Decision 005 — Smart MHC as Primary MHC Workspace

**Decision:** Smart MHC is the primary MHC workspace and the foundation for future automated customer reporting.

**Reason:** The v1.0.16 cleanup confirmed the legacy 01–08 MHC workflow and Executive Reports subsystem were redundant and safely removed.

**Status:** Approved — v1.0.16

## Decision 006 — Structured MHC Data Is the Report Source of Truth

**Decision:** Authoritative structured MHC data must feed Smart MHC presentation, MHC History, and the future Report Engine.

**Reason:** Canvas/widget state must not become a second engineering database or allow values to diverge from the actual MHC record.

**Status:** Approved — v1.0.16 direction

## Decision 007 — Customer Report Evolves the Excel Standard

**Decision:** The legacy customer Excel report is the engineering baseline for coverage and traceability, not the visual destination.

**Reason:** FSOS should modernize the communication of engineering results rather than reproduce a legacy spreadsheet in a new UI.

**Status:** Approved

## Decision 008 — Previous vs Current Is First-Class

**Decision:** Customer reporting must support explicit Previous vs Current comparison, especially for Laser Power and Beam Profile.

**Reason:** The customer explicitly requires comparison and the baseline must be traceable.

**Status:** Approved

## Decision 009 — Proven External Engines Are Protected

**Decision:** The proven Temperature and Laser Hour Monitor engines are integrated/migrated before any future enhancement.

**Reason:** Both engines were developed and proven outside FSOS. Rewriting stable high-value functionality during report work creates unnecessary regression risk.

**Status:** Approved — current Smart MHC phase

## Decision 010 — Temperature Engine Frozen for Current Phase

**Decision:** Do not redesign the Temperature Engine during the current Smart MHC report work. Migrate/integrate the proven engine only.

**Reason:** It already handles very large `.log` datasets and near-instant chart generation in its proven external implementation.

**Status:** Approved — current phase

## Decision 011 — Laser Hours Is Customer-Facing Report Data

**Decision:** Laser Hour Monitoring is a high-value customer report section.

**Reason:** Laser operating hours provide important asset/service context and should be communicated clearly, not hidden as internal-only telemetry.

**Status:** Approved

## Decision 012 — Report Visuals Follow Data Meaning

**Decision:** Each engineering parameter should use a visual representation appropriate to its data semantics.

**Examples:** specification bands, Previous/Current delta visuals, profile comparisons, optimization curves, adjustment scales, operating-band charts, quality evidence panels, calibration result panels, and action flows.

**Status:** Approved design direction

## Decision 013 — Laser Profile and Product Via Quality

**Decision:** Laser Profile primarily communicates the inspected customer product/process parameters. Product Via Quality communicates diameter, roundness, taper, and relevant evidence images.

**Status:** Approved

## Decision 014 — Stage & Scanner Calibration / AGC

**Decision:** Customer reporting should communicate Stage & Scanner Calibration / AGC results primarily as within-specification/out-of-specification outcomes with supporting images where useful.

**Reason:** The customer needs the calibration result and evidence; exact presentation will be designed from real samples.

**Status:** Approved

## Decision 015 — Requirement Verification Before Schema Expansion

**Decision:** Do not add engineering fields merely because an audit interprets them as customer requirements.

**Reason:** Actual customer workflow and real report/reference evidence outrank assumptions.

**Status:** Permanent rule

## Decision 016 — Free-First Infrastructure

FSOS will prefer existing/free/open-source infrastructure before paid services.

Any billable service requires explicit Founder approval after cost, growth, retention, and migration impact are understood.

**Status:** Approved

## Decision 017 — Image Persistence Deferred

R2 was identified as a technically suitable candidate for durable image storage, but it was not activated because it introduces a usage-based storage dependency.

The next step is to evaluate genuinely free/no-billing alternatives first.

**Status:** Deferred

## Decision 018 — Future Standalone Client

FSOS may evolve from browser-first to standalone desktop software using a local database and the existing sync architecture.

**Status:** Future

## Pending Decisions

- Image persistence architecture
- Authentication strategy
- User roles/permissions
- Multi-customer architecture
- Backup/disaster recovery
- Notification system
- Audit logging
- API versioning
- Desktop framework selection
- Final unified Report Engine data contract and renderer architecture

## Superseded Decisions

When an approved decision is replaced, retain the original decision, replacement, reason, effective version, and migration impact.
