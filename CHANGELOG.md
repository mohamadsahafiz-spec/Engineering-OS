# Engineering-OS Changelog

## v1.3.0 — FSOS Smart MHC & Report Engineering Governance

### Added
- Smart MHC is documented as the primary MHC workspace and the foundation for the future unified report engine.
- Customer-facing report evolution rules: the legacy Excel is the engineering baseline for coverage, not the visual/report destination.
- Planned unified report outputs: Full PDF, Compact one-page PDF, and PPTX.
- Previous vs Current comparison is a first-class reporting requirement, especially for Laser Power and Beam Profile.
- Data-type-driven visualization principle: each engineering parameter should use the clearest visual representation for its meaning rather than defaulting to tables.
- Proven-engine preservation rule: mature external engines are integrated and stabilized before future enhancement.
- FSOS Smart MHC report direction covering Laser Hours, Laser Power, Beam Profile, Focus Optimization, Power Offset, Product/Via Quality, Stage & Scanner Calibration/AGC, Temperature, Spare Parts, Findings/Actions, Evidence, and Buyoff.
- Rule that unverified requirements must not be invented from an audit interpretation; real customer workflow/evidence takes precedence.
- Atlas chat-context migration reminder as an engineering continuity safeguard: Atlas should proactively recommend a new chat when context becomes unwieldy and repeat the reminder if it is missed.

### Changed
- Updated FSOS project documentation from the former v1.0.14 foundation state to verified v1.0.16 after the controlled legacy cleanup.
- Removed obsolete Executive Reports and 01–08 MHC workflow from the documented active FSOS architecture.
- Reframed the future report engine around authoritative structured MHC data with Canvas as presentation, not a competing source of truth.
- Documented Temperature and Laser Hour engines as proven external engines to migrate/integrate without redesign during the current Smart MHC phase.
- Documented Laser Profile as customer/product/process context and Product Via Quality as a customer-facing quality/evidence area.
- Documented Stage & Scanner Calibration / AGC as a result-vs-specification report area with supporting images to be designed from real samples.

### Preserved
- Free-first infrastructure governance.
- D1 as authoritative structured server-side persistence.
- Workers as FSOS production runtime.
- R2 as not activated without explicit Founder approval.
- Future standalone desktop scope.
- Stable Temperature and Laser Hour engine logic.

## v1.2.0 — Governance & Engineering Discipline Upgrade

## v1.2.0 — Governance & Engineering Discipline Upgrade

### Added
- Evidence → Analysis → Root Cause → Fix → Verification as the standard investigation chain.
- Explicit Workers vs Pages pipeline identification.
- ZIP → GitHub → Cloudflare → Runtime repository/deployment comparison rule.
- Free-first infrastructure and explicit Founder approval for billable services.
- Runtime deployment identity verification guidance.
- Decision gates covering cost, lock-in, reversibility, and migration.
- Concise investigation log format.
- Mikasa normal reply target of under 50 words, with evidence-based exceptions.
- Exact-file editing guidance to prevent empty-shell implementations.
- Cloudflare Docs/MCP as an optional future engineering capability.

### Changed
- Consolidated the previous prompt-enhancement document into `00-Core/Prompt-Standard.md`.
- Strengthened CTO checklist evidence, cost, prompt enhancement, and deployment gates.
- Corrected stale Cloudflare technology status information.
- Corrected FSOS architecture documentation to reflect Workers as the production runtime and R2 as not yet activated.
- Updated FSOS project documentation to the verified v1.0.14 foundation state.
- Clarified that web → standalone desktop is a future architecture path, not current scope.
- Corrected README structure and repository links to match the actual repository.

### Removed
- Redundant `00-Core/Prompt Enhancement Principle 01.md`; its reusable rules are now consolidated into the Prompt Standard.

## v1.1.0

Initial Engineering-OS foundation.
