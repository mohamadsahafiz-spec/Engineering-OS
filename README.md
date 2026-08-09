# Engineering-OS v1.2.0 — Atlas Engineering Operating System

## Purpose

Engineering-OS is the permanent engineering governance, decision, prompt, template, project, and knowledge system used by Atlas and implementation agents such as Mikasa.

It is designed to protect engineering time, project stability, Founder resources, and long-term maintainability.

## Core Operating Model

```text
User Intent
    ↓
Evidence
    ↓
Analysis
    ↓
Root Cause
    ↓
Decision Gate
    ↓
Enhanced Prompt / Implementation
    ↓
Verification
    ↓
Documentation
```

## Repository Structure

```text
Engineering-OS/
├── README.md
├── CHANGELOG.md
├── metadata.json
├── 00-Core/
│   ├── Atlas-Constitution.md
│   ├── CTO-Checklist.md
│   ├── Decision-Making.md
│   ├── Engineering Principles.md
│   └── Prompt-Standard.md
├── 01-Templates/
│   ├── Sprint-Template.md
│   ├── Bugfix-Template.md
│   ├── Refactor-Template.md
│   ├── Migration-Template.md
│   ├── Architecture-Review.md
│   └── Release-Template.md
├── 02-Projects/
│   └── FSOS/
├── 03-Knowledge/
│   ├── Cloudflare.md
│   ├── Workers.md
│   ├── Pages.md
│   ├── D1.md
│   ├── R2.md
│   ├── KV.md
│   ├── SQLite.md
│   ├── React.md
│   ├── Electron.md
│   ├── Tauri.md
│   ├── Git.md
│   └── GitHub.md
└── 04-Archive/
    ├── Completed-Sprints.md
    └── Engineering-Lessons-EL-*.md
```

## Core Governance

Read `00-Core/` before making a material engineering decision. Core rules define evidence discipline, cost control, prompt quality, change control, and decision gates.

## Templates

Use `01-Templates/` for repeatable sprint, bugfix, migration, architecture, refactor, and release workflows.

## Projects

Project-specific architecture and roadmap information lives in `02-Projects/`. Projects inherit Core governance but maintain their own implementation details.

## Knowledge

`03-Knowledge/` contains practical technology guidance. Status labels must reflect verified current usage rather than historical assumptions.

## Archive

`04-Archive/` preserves completed work and reusable engineering lessons. Historical records should not be rewritten except to correct factual errors.

## Versioning

Engineering-OS follows Semantic Versioning:

- **MAJOR** — governance or structural overhaul.
- **MINOR** — new capabilities, rules, templates, or knowledge areas.
- **PATCH** — corrections and maintenance.

## Contribution Workflow

1. Identify the objective.
2. Inspect the current source of truth.
3. Establish evidence.
4. Propose or perform the smallest justified change.
5. Verify the result.
6. Update documentation/versioning when applicable.
7. Record reusable lessons.

## Current Version

**v1.2.0**

See [CHANGELOG.md](./CHANGELOG.md).
