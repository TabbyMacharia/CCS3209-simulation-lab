# CCS 3209 — Simulation and Modelling: Week 2 Lab

## Overview

This lab builds and progressively verifies, validates, calibrates, and experiments with a discrete-event simulation of an outpatient consultation queue. It moves from a hand-calculated deterministic baseline through a stochastic model, a calibration cycle against real reference data, a staffing-level experiment (1 vs. 2 officers), and a final sensitivity and credibility assessment.

No external simulation libraries are used — everything is built from scratch in Python (numpy for random number generation, no pandas, since it was blocked by a Windows Application Control policy on the development machine).

## Structure

The work follows the lab's six parts, each building on the last:

```text
Files
├── week2.py                          # Main notebook/script (Parts A–F)
├── stochastic_baseline_20reps.csv         # Part C: 20 baseline replications
├── stochastic_calibrated_20reps.csv         # Part C: 20 baseline replications
├── part_d_calibration_comparison.csv      # Part D: original vs. calibrated replications
├── part_e_scenario_comparison.csv         # Part E: 1-officer vs. 2-officer replications
├── part_f_sensitivity_analysis.csv        # Part F: demand sensitivity results
└── README.md
```

### Requirements
Python 3.x
numpy
matplotlib (for plots)
scipy (Part E confidence intervals)

No pandas dependency — CSV files are written using Python's built-in csv module.

## Running

Open week2_lab.py in PyCharm (or any Jupyter-compatible environment, given the #%% cell markers) and run cells top to bottom. A fixed random seed is used throughout each part for reproducibility.
