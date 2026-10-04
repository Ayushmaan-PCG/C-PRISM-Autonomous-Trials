# C-PRISM Trial Dataset

This repository contains the trial-level dataset used for the C-PRISM study.

## Dataset File

`C_PRISM_trial_data.csv`

## Dataset Structure

- 100 experimental run rows
- 50 baseline runs
- 50 C-PRISM runs
- 50 matched Pair IDs
- 28 columns
- UTF-8 comma-separated values (CSV)
- One header row
- Trial ID is unique for all 100 runs
- Each Pair ID contains exactly one baseline and one C-PRISM observation

## Important Missing-Value Note

One source value is blank:

- Trial **B13**: `Battery at start (V)`

This value was left blank intentionally in the submission copy because the source file does not contain a recorded value. No experimental value was estimated, imputed, or invented.

## Score Validation Against Manuscript Table 4

| Statistic | Value |
|---|---:|
| Baseline mean | 28.94 |
| C-PRISM mean | 79.30 |
| Baseline SD | 2.04 |
| C-PRISM SD | 2.54 |
| Mean paired gain | 50.36 |
| SD of paired gain | 3.22 |
| Baseline coefficient of variation | 7.06% |
| C-PRISM coefficient of variation | 3.20% |
| Paired t statistic, df = 49 | 110.65 |
| Approx. 95% CI for paired mean gain | [49.45, 51.27] |
| Cohen's d<sub>z</sub> | 15.65 |
| Cohen's d using pooled within-condition SD | 21.83 |
| Hedges' g | 21.67 |
| Gain range | 45 to 57 points |
| Positive paired gains | 50/50 |

These values reproduce the current manuscript Table 4 / Results calculations to the reported rounding.

## Data Dictionary

| Field | Description |
|---|---|
| `Trial ID` | Unique run identifier; `Bxx` = baseline, `Cxx` = C-PRISM. |
| `Pair ID` | Matched-pair identifier linking one baseline run and one C-PRISM run. |
| `Condition` | Experimental condition: `baseline` or `c_prism`. |
| `Order in pair` | Execution order within the matched pair. |
| `Route` | Autonomous route identifier used for the run. |
| `Start time` | Clock time at run start. |
| `End time` | Clock time at run end. |
| `Run duration (s)` | Elapsed run duration in seconds. |
| `Battery at start (V)` | Battery voltage measured at run start. |
| `Battery at end (V)` | Battery voltage measured at run end. |
| `Start position` | Standardized starting-position label. |
| `Start offset X (cm)` | Measured X-axis start-position offset in centimeters. |
| `Start offset Y (cm)` | Measured Y-axis start-position offset in centimeters. |
| `Start heading offset (deg)` | Measured starting heading offset in degrees. |
| `Autonomous score (points)` | Final autonomous score for the run. |
| `Task completion time (s)` | Time required to complete the autonomous task, in seconds. |
| `Timed out` | Binary indicator: `1` = timed out, `0` = did not time out. |
| `Failure events` | Count of recorded execution failure events during the run. |
| `Confidence triggers` | Count of low-confidence gating triggers. |
| `Total pause time (s)` | Total time spent paused because of confidence gating, in seconds. |
| `Recovery events` | Count of recovery/micro-correction events. |
| `Mean confidence (0 to 1)` | Mean C-PRISM/localization confidence value over the run. |
| `Minimum confidence (0 to 1)` | Minimum recorded confidence during the run. |
| `Final pose error (cm)` | Final localization/pose error in centimeters. |
| `Max path deviation (cm)` | Maximum recorded path deviation in centimeters. |
| `Field surface` | Field surface/setup label. |
| `Operator` | Operator identifier. |
| `Notes` | Run-specific observations recorded during testing. |

## Reproducibility Notes

- `Pair ID` should be used for paired statistical analyses.
- `Autonomous score (points)` is the primary outcome used in the manuscript.
- Rows should not be re-sorted or re-paired without retaining `Pair ID`.
- The blank B13 battery-start value should remain documented as missing unless an original contemporaneous record is available to supply it.
- This submission copy preserves the source dataset values; formatting cleanup did not alter experimental measurements or scores.
