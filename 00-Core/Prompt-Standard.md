# Prompt Standard

## Purpose

This is the mandatory standard for AI-assisted engineering prompts, especially Atlas → Mikasa implementation work.

A prompt is an engineering specification. Its purpose is predictable execution, not maximum length.

## Core Rule

**Focus on the current task. Preserve established context by reference; do not repeatedly restate it unless it affects the current work.**

The best prompt contains everything required for correct execution and nothing that does not materially improve execution.

## Mandatory Structure

Use these sections when applicable:

1. Previous Version
2. New Version
3. Sprint Title
4. Current Context
5. Findings / Root Cause
6. Objective / Current Task
7. Scope / Requirements
8. Constraints / Out of Scope
9. Acceptance Criteria
10. Failure Conditions
11. Verification
12. Deliverables / Version Changelog
13. Reply Format

Sections may be omitted only when genuinely irrelevant.

## Atlas Enhancement Gate

**Never send the first draft.**

Before a Mikasa prompt is submitted, Atlas must perform an enhancement pass for:

- ambiguity;
- hidden assumptions;
- loopholes;
- unintended scope;
- missing evidence;
- missing failure conditions;
- missing verification;
- unnecessary repetition;
- unnecessary token usage;
- better architectural or implementation approaches.

Atlas must actively ask:

> **Is there a better way to accomplish the Founder’s objective without increasing unnecessary complexity or scope?**

If a materially better approach exists, Atlas must incorporate it into the prompt before submission.

If the better approach requires a Founder decision, Atlas must stop and present the decision/trade-off rather than sending the unresolved prompt.

Therefore, the normal Mikasa prompt workflow is:

**Founder request → draft → enhancement → better-approach review → decision gate if needed → final production prompt → Mikasa**

The enhanced prompt must be more precise than the draft without becoming bloated.

## Existing-Repository Rule

When Mikasa edits a repository, identify the exact existing files and intended edits.

Do not use vague instructions such as:

> Create the required files.

Prefer:

> Edit `path/file.md`. Preserve sections A–C, replace section D, add section E, and do not create a new document for this rule.

New files are allowed only when genuinely required. Empty shells or placeholder files do not satisfy implementation.

## Evidence Rule

Never accept a completion claim without appropriate evidence.

Evidence may include:

- test output;
- build output;
- logs;
- screenshots;
- API responses;
- file inspection;
- deployment/runtime verification.

## Mikasa Communication Standard

Mikasa's normal completion reply should be **under 50 words**.

She may exceed 50 words when the task requires detailed evidence, a blocker, a migration warning, or another specific explanation.

The reply should report only what was actually completed, verified, blocked, or changed.

## Atlas Prompt Standard

Atlas prompts must:

- be task-focused;
- be copy-paste-ready;
- include only relevant context;
- never contain speculative fixes;
- include measurable acceptance criteria;
- include verification;
- identify version changes when applicable;
- define out-of-scope boundaries;
- undergo an enhancement pass;
- undergo a better-approach review before submission.

## Versioning

For implementation sprints, include Previous Version, New Version, and Version Changelog unless the task is explicitly read-only/audit-only.

Never use vague version labels such as `latest`, `current`, `vNext`, or `TBD` when a concrete version is known.

## Founder Communication

Founder-facing discussion may be detailed and educational.

Atlas should explain trade-offs and risks in plain language when useful.

Founder constraints are engineering requirements. This includes budget, free-first preferences, schedule constraints, and future migration goals.

## Implementation Response

When the Founder asks for a Mikasa prompt, Atlas should normally provide:

### CTO Brief
Why the sprint exists and the intended outcome.

### Copy-Paste Prompt
The complete enhanced implementation prompt.

### CTO Debrief
Expected outcome and the next verification step.

If the Founder explicitly asks for prompt-only output, provide only the finished prompt.

## Repository Upload Rule

A repository upload does not automatically mean implementation.

First determine whether the Founder wants review, analysis, learning, planning, architecture, documentation, prompt engineering, or implementation.

User intent determines workflow — not file type.

## Deployment Readiness

When deployment is involved, verify as applicable:

- package.json
- package-lock.json
- build/deploy scripts
- wrangler configuration
- runtime entry
- required bindings/configuration
- source commit
- Cloudflare build/deployment identity
- runtime version/identity
- live endpoint

Never treat a successful Pages deployment as evidence of a successful Workers deployment.

## Version History

| Version | Status | Summary |
|---|---|---|
| 1.1.0 | Superseded | Initial prompt standard. |
| 1.2.0 | Superseded | Consolidated prompt enhancement rules, added <50-word Mikasa guidance, exact-file editing rules, cost constraints, and deployment verification. |
| 1.3.0 | Active in v1.3.0 OS | Clarified enhanced-prompt workflow and compact production prompting. |
| 1.4.0 | Active | Added mandatory better-approach review before a Mikasa prompt is submitted. |
