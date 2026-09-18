# Hartford Logic Benchmark v1.0

**Deterministic Evidence-State Measurement**

Hartford Logic Benchmark v1.0 is a controlled synthetic falsification benchmark for deterministic evidence-state measurement.

It evaluates whether admitted evidence establishes a single operationally defensible state or whether materially different states remain supported under published evidence requirements and constraints.

## Benchmark

The benchmark contains 80 synthetic operational events evaluated across six evidentiary stages, producing 480 event-stage classifications.

The operational records remain fixed across all stages. Only the admitted temporal evidence changes.

**Predetermined classifications:** 480  
**Observed classifications:** 480  
**Matches:** 480

A separate post-run closed-form mathematical recomputation matched both the predetermined and observed classifications in all 480 comparisons. Repeated execution with unchanged evidence and configuration produced identical substantive results.

## Reproduce or Challenge the Result

Start with:

- `Hartford_README.md` for benchmark orientation
- `Hartford_Benchmark_Specification.md` for the mathematical and classification rules
- `Hartford_Temporal_Evidence.json` for the admitted temporal evidence
- `Hartford_Predetermined_Classifications.csv` for the predetermined classifications
- `Hartford_Observed_Classifications.csv` for the observed classifications
- `Hartford_Worked_Examples.md` for manual calculations
- `Hartford_Challenge.md` for falsification instructions
- `Hartford_SHA256_Manifest.txt` for file-integrity verification

The benchmark does not determine what actually happened or select a most-likely history. It measures whether the admitted evidence has earned one materially defensible operational state under the stated assumptions and constraints.

## Scope

This is a controlled synthetic benchmark. Temporal uncertainty provides bounded conditions that can be directly calculated and falsified.

The benchmark evaluates the published classifications under the stated evidence, assumptions, and constraints. It does not constitute external real-world validation.

## Archive

The immutable archival copy of Hartford Logic Benchmark v1.0 is deposited with Zenodo under DOI 10.5281/zenodo.22730361.

## Hartford Logic

**Where evidence ends and judgment begins.**

Hartford Logic's patent-pending technology performs deterministic evidence-state measurement before a human, AI, or automated system acts on evidence.

Hartford Logic measures the evidentiary condition. The downstream system determines what to do about it.

© 2026 Hartford Logic LLC. All rights reserved.
