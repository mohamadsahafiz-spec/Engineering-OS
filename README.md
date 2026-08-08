# Atlas-OS v1.1.0 — Engineering Operating System

## Purpose
Atlas-OS is a documentation-only engineering operating system designed to serve as the permanent operating manual, decision framework, and architecture scaffolding for software projects.

## Scope
Covers all core governance, operational templates, project definitions, knowledge bases, and retrospective archives across all current and future engineering initiatives.

## When to Use
Consult Atlas-OS at the onset of new projects, during sprint planning, architecture reviews, bug triage, refactoring, and release workflows.

## Related Documents
- [00-Core Governance](./00-Core/Atlas-Constitution.md)
- [01-Templates Catalog](./01-Templates/Sprint-Template.md)
- [02-Projects Registry](./02-Projects/FSOS/Project.md)
- [03-Knowledge Base](./03-Knowledge/Cloudflare.md)
- [04-Archive](./04-Archive/README.md)

## Repository Structure
```
Atlas-OS/
├── README.md
├── 00-Core/
│   ├── Atlas-Constitution.md
│   ├── CTO-Checklist.md
│   ├── Prompt-Standard.md
│   ├── Prompt-Enhancement-Guide.md
│   ├── Engineering-Principles.md
│   └── Decision-Making.md
├── 01-Templates/
│   ├── Sprint-Template.md
│   ├── Bugfix-Template.md
│   ├── Refactor-Template.md
│   ├── Migration-Template.md
│   ├── Architecture-Review.md
│   └── Release-Template.md
├── 02-Projects/
│   ├── FSOS/
│   ├── Vault/
│   ├── SmartHome/
│   └── IdleGame/
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
    ├── Completed-Sprints/
    ├── Retrospectives/
    └── Lessons-Learned/
```

## How Atlas-OS is Used
1. **Core Governance**: Reference `00-Core/` for engineering policies, prompts, and decision guidelines.
2. **Execution via Templates**: Instantiate operational templates from `01-Templates/` into project sprint directories.
3. **Project Management**: Track active project specs, architecture, and roadmaps in `02-Projects/`.
4. **Knowledge Sharing**: Access technology guidelines and best practices in `03-Knowledge/`.
5. **Historical Archiving**: Archive finalized sprint reports and retrospectives in `04-Archive/`.

## Versioning Strategy
Atlas-OS follows Semantic Versioning (`MAJOR.MINOR.PATCH`):
- `MAJOR`: Structural changes or overhaul of core principles.
- `MINOR`: New templates, project additions, or knowledge expansions.
- `PATCH`: Formatting fixes, link corrections, and template minor edits.

## Contribution Workflow
1. Branch off `main`.
2. Propose modifications to core documents or new templates via Pull Request.
3. Conduct Architecture & Governance review.
4. Merge and bump Atlas-OS version.
