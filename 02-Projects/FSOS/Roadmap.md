# FSOS Roadmap

## Current: v1.1.16 candidate status

### Completed

- zero-state / ghost-data cleanup;
- authoritative Customer identity reconciliation;
- Machine Passport foundation;
- Smart MHC engineering foundation;
- Recommended Parts Master;
- Temperature graph reload/display fix;
- Temperature Inspection Delete persistence fix.

## Immediate next

### Legacy UI cleanup continuation

Remove **Mission Control** completely from UI/navigation and delete only its genuinely orphaned route/module code. Leave **Daily Work** as the only item under the DAILY WORK section.

Protected during this task:
- MHC Autopilot;
- Canvas / Workspace;
- MHC History;
- Machine Passport;
- Operations;
- StorageService / SyncEngine;
- MHC session architecture;
- Report Engine / Full PDF.

Verification must include tests, typecheck, production build, Daily Work functionality, and initialization of core MHC workflows.

### Engineering boundary

Do not reopen stable core architecture or historical Temperature work without new evidence. Follow `FSOS-Current-State.md` as the active project-state source.

## After chart stabilization

1. Study the complete customer MHC report.
2. Map report requirements to Smart MHC / Report Studio.
3. Identify genuine gaps.
4. Improve report traceability.
5. Design MHC Autopilot current-condition recommendations.
6. Resolve recommendations only against authoritative Recommended Parts records.

## Parked

### Predictive maintenance

Do not implement yet.

Future inputs may include:
- laser hours;
- MHC history;
- drift/trends;
- temperature history;
- beam-profile history;
- replacement history;
- recommended lifespan;
- service history.

The eventual system should provide conservative risk/attention guidance, not pretend to know an exact failure date.
