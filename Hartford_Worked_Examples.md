# Hartford Worked Examples

These examples show how a published classification can be checked directly from the disclosed
records, temporal evidence, and benchmark specification.

## UNIQUE example: S3, MA-20260815-1343

Recorded verification: `2026-08-15T17:10:32Z`  
Pump start: `2026-08-15T17:10:35Z`

At S3, E2 and E3 both apply to this post-breakpoint MED-WS-11 verification event.
Their intervals are intersected. Both intervals are centered on the same recorded event time, and E3 is the tighter applicable bound:

`R(t) = 2.40 + (60 × 10^-6 × 32) = 2.40192 seconds`

The latest admissible verification time is therefore:

`17:10:32 + 2.40192 = 17:10:34.40192`

That remains strictly before the pump start at `17:10:35`.

**Classification: UNIQUE**

## MULTIPLE_ADMISSIBLE example: S1, MA-20260815-1303

Recorded verification: `2026-08-15T17:00:32Z`  
Pump start: `2026-08-15T17:00:33Z`  
Anchor: `2026-08-15T09:00:00Z`  
Elapsed time from anchor: `28,832 seconds`

`R(t) = 0.20 + (100 × 10^-6 × 28,832) = 3.0832 seconds`

The admissible verification interval extends from:

`17:00:28.9168` through `17:00:35.0832`.

Equivalently, a displacement of `-3.0832` seconds leaves verification before pump start, while a
displacement of `+3.0832` seconds places verification after pump start.

The same admitted evidence therefore permits materially different temporal orderings.

**Classification: MULTIPLE_ADMISSIBLE**
