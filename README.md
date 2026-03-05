# C-PRISM Autonomous Trial Summary Dataset

This repository contains the summarized experimental dataset used in the manuscript:

**“C-PRISM: Cognitaur Probabilistic Runtime Inference and Sensor Model for Robust VEX Autonomous Navigation.”**

## Dataset Description

The dataset includes **50 paired autonomous trials** conducted on a VEX V5 robot:
- 50 baseline runs (no probabilistic confidence gating)
- 50 C-PRISM runs (with probabilistic runtime inference and confidence-based recovery)

Each pair corresponds to identical routes, start poses, field conditions, and hardware configuration.

## Data Origin

- **Robot telemetry** was recorded using the VEX V5 Brain during each autonomous run.
- **Scores** were recorded manually immediately after each run by visual inspection following official VEX Skills Challenge scoring rules.
- Raw telemetry was post-processed to produce per-run summary metrics.

## What This Dataset Contains

Each row represents a single autonomous run and includes:
- Trial identifiers and condition labels
- Run timing (start/end timestamps without calendar dates)
- Battery voltage at start and end of run
- Initial pose offsets
- Autonomous score (manual count)
- Confidence-trigger counts and recovery events
- Final pose error and maximum deviation
- Field surface and operator metadata

## What This Dataset Does NOT Contain

- No raw millisecond-level pose telemetry
- No video data
- No personal or identifying information
- No duplicated or synthetic runs

The provided dataset corresponds exactly to the data used for statistical analysis and figures in the manuscript.

## Usage

This dataset is intended for:
- Reproducibility verification
- Independent statistical analysis
- Educational and research use

For questions or clarifications, please refer to the associated manuscript.
