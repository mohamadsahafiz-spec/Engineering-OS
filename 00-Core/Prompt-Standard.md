# Prompt Standard

## Purpose

This document defines the mandatory prompt standard used throughout Engineering-OS.

Every prompt written for AI-assisted engineering shall follow this structure unless explicitly exempted.

The objective is to maximize predictability, minimize ambiguity, reduce iteration cycles, and produce verifiable engineering outcomes.

---

# Philosophy

A prompt is an engineering specification.

It should communicate intent with enough precision that the AI cannot reasonably misunderstand the task.

A good prompt reduces interpretation.

An excellent prompt eliminates it.

---

# Mandatory Prompt Structure

Every engineering prompt shall follow this order.

---

## Previous Version

State the current version before changes.

Example

Previous Version:
v0.9.1

---

## New Version

Specify the version after completion.

Example

New Version:
v0.9.2

---

## Sprint

Provide a concise sprint title.

Example

Sprint:
Cloud Sync Reliability

---

## Objective

Describe the primary outcome in one clear paragraph.

Focus only on the current sprint.

Avoid unrelated context.

---

## Scope

Explicitly define what is included.

Example

Included:

- Cloud sync
- Error handling
- Logging

---

## Out of Scope

Explicitly define what must not be modified.

Example

Do NOT modify:

- UI
- Database schema
- Existing workflows
- Authentication

---

## Requirements

Describe implementation requirements.

Prefer concise bullet points.

Avoid vague language.

---

## Constraints

State implementation limits.

Examples

- Preserve backwards compatibility.
- Maintain existing architecture.
- Do not introduce unnecessary dependencies.
- Avoid duplicate logic.

---

## Acceptance Criteria

Every requirement must be objectively verifiable.

Good examples

✓ API returns JSON

✓ File exists

✓ Tests pass

✓ Build succeeds

✓ UI unchanged

Poor examples

✗ Works correctly

✗ Looks good

✗ Better performance

---

## Failure Conditions

Define what constitutes failure.

Examples

The task is incomplete if:

- Any existing feature breaks.
- Any file is removed unintentionally.
- Acceptance criteria are not met.
- Manual intervention is required.

---

## Verification

List the steps required to verify success.

Example

1. Build project.
2. Execute tests.
3. Verify API response.
4. Confirm files exist.
5. Confirm version updated.

---

## Deliverables

Specify exactly what must be produced.

Examples

- Updated source code
- Documentation
- Migration notes
- Changelog
- Version increment

---

## Reply Format

Require concise status reporting.

Example

Completed.

Build:
PASS

Tests:
PASS

Blockers:
None

---

# Engineering Rules

Every prompt shall:

- solve one problem
- avoid feature creep
- preserve existing architecture
- minimize token usage
- maximize clarity
- define measurable success
- define measurable failure
- require verification

---

# Versioning Rule

Every implementation prompt shall update:

- version number
- changelog
- release notes (when applicable)

No implementation is complete without version tracking.

---

# Golden Rules

1. One sprint, one objective.

2. Never combine unrelated work.

3. Protect existing functionality.

4. Prevent assumptions.

5. Verify before claiming success.

6. Observable evidence is mandatory.

7. Keep prompts compact without sacrificing precision.

8. Prefer engineering language over conversational language.

9. Every prompt must be reviewed once before submission.

10. Every prompt should leave less room for interpretation than the previous version.

---

# Atlas Review Checklist

Before sending any prompt, Atlas must confirm:

✓ Objective is clear.

✓ Scope is limited.

✓ Constraints are defined.

✓ Acceptance criteria are observable.

✓ Failure conditions exist.

✓ Verification steps exist.

✓ Deliverables are listed.

✓ Reply format is specified.

Only then may the prompt be considered complete.