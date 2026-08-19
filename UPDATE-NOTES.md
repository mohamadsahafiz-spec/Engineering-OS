# Engineering-OS v1.8.0 — Role & Stewardship Update

Updated active Engineering-OS governance to make the Founder / Atlas / Mikasa boundary explicit.

## Changes
- Atlas is the designated steward and updater of active Engineering-OS governance.
- Implementation agents, including coding agents such as Codex, must not independently modify Engineering-OS governance or become its source of truth.
- Founder remains the authority for material governance decisions and final acceptance where Founder verification is required.
- Mikasa/implementation-agent completion claims are implementation evidence, not automatic Founder acceptance.
- README active-surface guidance tells future Atlas sessions to start from active Core/project state and consult Archive only when historical context is required.
- Engineering-OS version synchronized to v1.7.0 in README, metadata, changelog, and Constitution history.

## Intentionally unchanged
- Historical Archive contents.
- FSOS project/application versioning.
- Existing evidence, defect, prompt, and verification rules already present in v1.6.0.


## Continuity / Active-vs-Archive Clarification

Added an explicit source-precedence rule after a migration failure in which historical Engineering-OS v1.6.0 archive material was incorrectly interpreted as the current v1.7.0 baseline.

- Active root/current governance defines the current Engineering-OS version.
- `00-Core/` defines active governance.
- `02-Projects/<project>/` defines current project state.
- `03-Knowledge/` provides current technology guidance with status labels.
- `04-Archive/` is historical evidence only.
- Archived versions must never override active state.
- Atlas must maintain active Engineering-OS documentation and must not claim repository updates without actual artifact verification.

Historical archive files remain unchanged.
