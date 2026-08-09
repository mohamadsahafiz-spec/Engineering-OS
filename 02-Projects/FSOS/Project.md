# FSOS (Field Service Operations System)

## Project Status

- **Status:** Active Development
- **Verified Version:** v1.0.14
- **Foundation:** Green / verified
- **Remaining Foundation Issue:** Durable cross-device image persistence
- **Priority:** High
- **Owner:** Sahafiz
- **Lead Architect:** Atlas
- **Implementation Engineer:** Mikasa

## Purpose

FSOS is an engineering operations platform for field service execution, Machine Health Checks, machine data, reporting, contract management, and operational intelligence.

## Vision

Build a reliable engineering operating platform that enables field engineers to execute work efficiently, manage operational data, generate professional reports, and synchronize information across multiple devices.

## Verified Technology Stack

Frontend

- React
- Vite
- Tailwind
- Cloudflare Worker static assets / frontend delivery

Backend

- Cloudflare Workers

Database

- Cloudflare D1

Version Control

- Git
- GitHub

Future / Not Yet Active

- R2 for durable image storage
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

Remaining red capability:

- Image persistence across devices
- Server-side image deletion

## Current Objectives

1. Resolve image persistence without introducing an unapproved recurring service cost.
2. Preserve the verified synchronization foundation.
3. Continue operational modules only after foundation risk is controlled.

## Long-Term Architecture Direction

FSOS may evolve from a browser-first application into standalone desktop software.

Future direction:

**Standalone Client → Local Database → Sync Engine → Cloudflare Worker → D1**

This is future scope, not current implementation work.

## Engineering Principles

FSOS follows Engineering-OS Core governance. Project decisions must respect evidence discipline, cost constraints, change control, and verification requirements.

## Revision Policy

Update this document when verified project architecture, status, or major decisions change. Do not use it as a sprint backlog.
