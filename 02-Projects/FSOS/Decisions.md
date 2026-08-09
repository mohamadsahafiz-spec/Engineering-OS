# FSOS Engineering Decisions

## Document Status

- **Status:** Living Document
- **Verified Version:** v1.0.14
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

## Decision 005 — Modular Workspaces

FSOS remains modular across Dashboard, Mission Control, Machine Passport, MHC, Report Studio, Contract Management, Planner, and Settings.

**Status:** Approved

## Decision 006 — Offline Capability

Offline capability remains a long-term requirement.

**Status:** Planned

## Decision 007 — Multi-Device Synchronization

Cloud synchronization is a core capability and must remain reliable across devices.

**Status:** Verified foundation

## Decision 008 — AI-Assisted Engineering

Atlas provides architecture, investigation, governance, and prompts. Mikasa implements approved work.

**Status:** Approved

## Decision 009 — Quality Before Speed

Engineering quality takes priority over development speed. Urgency does not justify unsupported assumptions.

**Status:** Approved

## Decision 010 — Free-First Infrastructure

FSOS will prefer existing/free/open-source infrastructure before paid services.

Any billable service requires explicit Founder approval after cost, growth, retention, and migration impact are understood.

**Status:** Approved

## Decision 011 — Image Persistence Deferred

R2 was identified as a technically suitable candidate for durable image storage, but it was not activated because it introduces a usage-based storage dependency.

The next step is to evaluate genuinely free/no-billing alternatives first.

**Status:** Deferred

## Decision 012 — Future Standalone Client

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

## Superseded Decisions

When an approved decision is replaced, retain the original decision, replacement, reason, effective version, and migration impact.
