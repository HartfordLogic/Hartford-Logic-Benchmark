# Hartford Challenge

## Purpose

Given the admitted evidence, has the required ordering been established to a single operationally
defensible state, or do materially different states remain supported?

The benchmark evaluates the strict material relationship:

`VERIFIED_FOR_ADMINISTRATION < INFUSION_STARTED`

The designated verification event comes from `Hartford_Medication_Transitions.jsonl`.
The designated pump-start event comes from `Hartford_Infusion_Pump_Status.csv`.
Corresponding records are joined by `med_event_id`.

## Benchmark terminology

The technical benchmark classifications map to Hartford Logic's public result terminology as follows:

- `UNIQUE` = **RESOLVED**
- `MULTIPLE_ADMISSIBLE` = **MULTIPLE STATES**

## Reproduce the classifications

For each event and stage:

1. Identify the temporal evidence admitted at that stage in `Hartford_Temporal_Evidence.json`.
2. Determine which published constraints apply to the designated verification event.
3. For each applicable constraint calculate:
   `R(t) = O + (P × 10^-6) × |t - t_anchor|`.
4. Convert each applicable bound to its closed admissible event-time interval.
5. If multiple constraints apply, intersect their intervals. Confirm that the resulting intersection is non-empty.
6. Treat the pump-start timestamp as the benchmark reference side with no added uncertainty.
7. Classify `UNIQUE` only if the latest admissible verification time remains strictly before pump start.
8. Classify `MULTIPLE_ADMISSIBLE` when the admitted interval permits both a before-pump ordering and
   an at-or-after-pump ordering.
9. Compare the result with `Hartford_Predetermined_Classifications.csv`.

For all 480 published cases, the final admissible verification interval contains at least one time
strictly before pump start. The benchmark therefore exercises only the two published categories,
`UNIQUE` and `MULTIPLE_ADMISSIBLE`; no case is an all-at-or-after-pump violation case.

## Falsify a published classification

For a published `UNIQUE` classification, produce a materially different temporal ordering that
satisfies the same published evidence and benchmark constraints.

For a published `MULTIPLE_ADMISSIBLE` classification, demonstrate that the same published evidence
and constraints force the strict-before relationship for every admissible verification time.

Any defensible method may be used. Access to Hartford Logic's implementation is not required.

A challenge that changes the published evidence, adds an unstated assumption, or substitutes a
different benchmark rule is a methodological critique or alternative experiment, not a falsification
of the published classification. Such critiques may still be useful and should identify the changed
assumption explicitly.

## Scope

This is a controlled synthetic benchmark of deterministic evidence-state measurement. Temporal
uncertainty is the experimental mechanism. The benchmark does not establish performance,
scalability, universal applicability, or external real-world validation.
