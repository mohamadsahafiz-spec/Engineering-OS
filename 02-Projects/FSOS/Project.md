# FSOS (Field Service Operations System)

## Project Status

- **Status:** Active Development
- **Verified Version:** v1.0.16
- **Foundation:** Green / verified
- **Remaining Foundation Issue:** Durable cross-device image persistence
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

## Current Foundation Status

Verified green:

- Workers deployment
- GitHub → Cloudflare deployment chain
- D1 authoritative persistence
- Create/Edit/Delete synchronization
- Full-sync deletion reconciliation
- D1 migrations and indexes
- Runtime version/deployment identity
- Version consistency
- Deployment reproducibility
- Local/production parity
- v1.0.15 large-temperature-log quota optimization and IndexedDB raw telemetry offload
- v1.0.16 controlled removal of obsolete MHC 01–08 and Executive Reports architecture

Remaining red capability:

- Durable cross-device image persistence
- Server-side image deletion

R2 remains inactive under free-first cost governance.

## Smart MHC — Current Primary Workspace

Smart MHC is the primary MHC workspace and the foundation for the future unified report engine.

The controlled v1.0.16 cleanup removed the obsolete 01–08 MHC wizard and Executive Reports subsystem. MHC History and Machine Passport remain active.

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

## MHC Report Evolution

The legacy customer Excel report is the engineering baseline for coverage and traceability, not the visual destination.

FSOS should evolve the report by:

- reorganizing information around customer understanding;
- automating calculations and comparisons;
- using visualizations appropriate to each data type;
- preserving evidence and traceability;
- clearly separating current condition, previous baseline, findings, actions, and recommendations.

The report should make it easy for a customer to understand:

**What was checked → what changed → whether it is within specification → what was found → what was done → what evidence supports the result → what should happen next.**

### High-Value Report Areas

- Laser Hour Monitoring
- Laser Power
- Beam Size / Beam Profile
- Focus Optimization
- Power Offset
- Product / Laser Profile information
- Product Via Quality: diameter, roundness, taper, and images
- Stage & Scanner Calibration / AGC
- Temperature Monitoring
- Spare Part Recommendations
- Findings and Corrective Actions
- Evidence
- Engineer / Customer Buyoff

### Comparison Requirement

Previous vs Current comparison is a core requirement.

At minimum, the report architecture must support explicit historical comparison for:

- Laser Power
- Beam Profile

The comparison baseline must be explicitly selectable and traceable rather than implicitly chosen from an arbitrary first historical session.

### Proven External Engines

#### Temperature Engine — FROZEN FOR CURRENT PHASE

The temperature engine was developed and proven outside FSOS and can process very large `.log` files with near-instant chart generation. The current Smart MHC report phase must not redesign or replace this engine.

Current direction:

**Proven engine → migrate/integrate → report**

Future optimization is allowed only as a separate enhancement phase after the current report foundation is stable.

#### Laser Hour Monitor — FROZEN FOR CURRENT PHASE

The Laser Hour Monitor was also developed and proven outside FSOS. Its engine should be migrated/integrated into FSOS and represented prominently in the customer report.

Do not redesign a proven engine during the current Smart MHC report phase.

### Other Report Semantics

**Laser Profile** is primarily customer/product/process context: what product and parameters were used/inspected. It should remain useful but should not be over-engineered.

**Product Via Quality** is a customer-facing quality result and evidence area covering diameter, roundness, taper, and relevant images.

**Stage & Scanner Calibration / AGC** should primarily communicate the calibration result against specification, with supporting calibration images where useful. Exact presentation should be designed from real samples.

### Requirement Verification Rule

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
