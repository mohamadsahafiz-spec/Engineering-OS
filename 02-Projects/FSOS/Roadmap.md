# FSOS Roadmap

## Current: v1.0.37

### Completed

- zero-state / ghost-data cleanup;
- authoritative Customer identity reconciliation;
- Machine Passport foundation;
- Smart MHC engineering foundation;
- Recommended Parts Master;
- Temperature graph reload/display fix;
- Temperature Inspection Delete persistence fix.

## Immediate next

### Temperature Chart Controls

Add explicit chart controls for:

**X-axis**
- selectable major time interval (for example 1h, 2h, 3h, 6h, etc.).

**Y-axis**
- predictable major-step/range behavior;
- no unwanted automatic range changes when fixed behavior is selected.

**Channels**
- temperature has six channels; chart/preview behavior must not accidentally expose only CH1 when the underlying record contains CH1–CH6.

### Engineering boundary

Do not redesign the proven Temperature Engine simply to implement chart controls.

First establish:
`raw telemetry → existing resampling/aggregation → chart data → renderer`

Then decide whether the new interval belongs to:
- chart-only presentation; or
- an existing engineering aggregation boundary.

Raw telemetry must remain intact.

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
