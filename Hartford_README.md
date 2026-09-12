# Hartford Benchmark v1.0

Controlled synthetic falsification benchmark for deterministic evidence-state measurement under
bounded temporal uncertainty.

## What is being tested

The benchmark holds 80 synthetic operational events constant across six evidentiary stages.
Only admitted temporal evidence changes. The four operational-record files remain byte-for-byte fixed across stages.

For each event, the material requirement is whether the designated
`VERIFIED_FOR_ADMINISTRATION` transition is established strictly before the corresponding
`INFUSION_STARTED` event.

The benchmark asks:

**Given the admitted evidence, has the required ordering been established to a single operationally
defensible state, or do materially different states remain supported?**

## Published result

The predetermined stage progression is:

`80/0 → 70/10 → 65/15 → 70/10 → 75/5 → 80/0`

where each pair is `UNIQUE / MULTIPLE_ADMISSIBLE`.

Hartford Logic's first controlled execution matched all 480 predetermined classifications.
A separate post-run mathematical recomputation also matched all 480.

## Start here

1. Read `Hartford_Benchmark_Specification.md`.
2. Inspect the four fixed operational-record files.
3. Read `Hartford_Temporal_Evidence.json`.
4. Recompute the classifications without using the answer key.
5. Compare your results with `Hartford_Predetermined_Classifications.csv`.
6. Compare the published first-execution classifications in `Hartford_Observed_Classifications.csv`.
7. Use `Hartford_Challenge.md` for the falsification criteria.
8. See `Hartford_Worked_Examples.md` for two manual checks.

No Hartford Logic source code is required to challenge a published classification.

## Files

- `Hartford_Medication_Orders.csv`
- `Hartford_Medication_Transitions.jsonl`
- `Hartford_Medication_Observations.csv`
- `Hartford_Infusion_Pump_Status.csv`
- `Hartford_Temporal_Evidence.json`
- `Hartford_Benchmark_Specification.md`
- `Hartford_Predetermined_Classifications.csv`
- `Hartford_Observed_Classifications.csv`
- `Hartford_Worked_Examples.md`
- `Hartford_Challenge.md`
- `Hartford_Validation_Summary.md`
- `Hartford_Version.txt`
- `Hartford_SHA256_Manifest.txt`

## Scope

This is a controlled synthetic benchmark of deterministic evidence-state measurement. Temporal uncertainty is used because it provides bounded conditions that can be directly calculated and falsified.

The benchmark evaluates the published classifications under the stated evidence, assumptions, and constraints. It does not constitute external real-world validation.
