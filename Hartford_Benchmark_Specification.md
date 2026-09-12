# Hartford Benchmark Specification

## Benchmark question

**Given the admitted evidence, has the required ordering been established to a single operationally defensible state, or do materially different states remain supported?**

## Benchmark record

The benchmark contains 80 controlled synthetic operational events evaluated across six evidentiary stages, S0 through S5. The operational-record files remain unchanged across all stages.

Corresponding records are linked by `med_event_id`.

The designated material relationship is:

`VERIFIED_FOR_ADMINISTRATION < INFUSION_STARTED`

The designated verification event is selected from `Hartford_Medication_Transitions.jsonl` where `to_state = VERIFIED_FOR_ADMINISTRATION`. Its timestamp field is `event_utc`.

The designated pump-start event is selected from `Hartford_Infusion_Pump_Status.csv` where `pump_state = INFUSION_STARTED`. Its timestamp field is `event_utc`.

`Hartford_Medication_Orders.csv` and `Hartford_Medication_Observations.csv` are retained as part of the fixed heterogeneous operational record but are not the designated event pair for the material temporal relationship.

## Temporal model

For each applicable temporal constraint:

`R(t) = O + (P × 10^-6) × |t - t_anchor|`

where:

- `O` is the published offset bound in seconds.
- `P` is the published rate bound in parts per million.
- `t` is the recorded verification timestamp.
- `t_anchor` is the published anchor timestamp.

Each applicable constraint defines a closed admissible verification-time interval:

`[t_recorded - R(t), t_recorded + R(t)]`

When more than one published temporal constraint applies to the same event, the final admissible verification-time interval is the intersection of all applicable intervals.

All time differences used in the calculation are measured in seconds.

## Evidence stages

At S0, no additional temporal-characterization evidence is admitted. Recorded timestamps are used at face value.

At S1 through S5, temporal evidence is admitted cumulatively as published in `Hartford_Temporal_Evidence.json`.

For MED-WS-11, the published correction breakpoint is `2026-08-15T17:10:00Z`:

- `PRE` means the recorded verification timestamp is before the breakpoint.
- `POST` means the recorded verification timestamp is at or after the breakpoint.
- `UNCHARACTERIZED_FACE_VALUE` means no published temporal-characterization evidence applies to that event at that stage, so its recorded timestamp is used at face value for benchmark classification.

## Reference-side assumption

For this controlled benchmark, pump-start timestamps are treated as the reference side with no additional temporal uncertainty.

## Technical benchmark classifications

The benchmark uses two technical classification labels:

### `UNIQUE` (Hartford Logic public result: **RESOLVED**)

The latest time in the final admissible verification interval is strictly before pump start. Under the published evidence and constraints, only the required material ordering remains supported.

### `MULTIPLE_ADMISSIBLE` (Hartford Logic public result: **MULTIPLE STATES**)

The final admissible verification interval permits both a before-pump ordering and an at-or-after-pump ordering. Materially different temporal states therefore remain supported.

For all 480 published event-stage cases, the final admissible verification interval contains at least one time strictly before pump start. The benchmark therefore exercises only these two technical categories; no published case is entirely at or after pump start.

## Predetermined stage totals

| Stage | UNIQUE | MULTIPLE_ADMISSIBLE |
|---|---:|---:|
| S0 | 80 | 0 |
| S1 | 70 | 10 |
| S2 | 65 | 15 |
| S3 | 70 | 10 |
| S4 | 75 | 5 |
| S5 | 80 | 0 |
