## CCS 3209 — Simulation and Modelling: Week 2 Lab

Overview

This lab builds and progressively verifies, validates, calibrates, and experiments with a discrete-event simulation of an outpatient consultation queue. It moves from a hand-calculated deterministic baseline through a stochastic model, a calibration cycle against real reference data, a staffing-level experiment (1 vs. 2 officers), and a final sensitivity and credibility assessment.

No external simulation libraries are used — everything is built from scratch in Python (numpy for random number generation, no pandas, since it was blocked by a Windows Application Control policy on the development machine).

Structure

The work follows the lab's six parts, each building on the last:

Part	Focus	Key output
A	Conceptual model & deterministic baseline	Entity/resource/event specification, hand-calculated 6-patient table, five verification assertions
B	Implementation & verification	Event trace matching the manual table, assertions programmed into the model, four extreme-condition tests
C	Stochastic model & validation	20 replications (exponential arrivals, triangular service times) compared against a 10-day observed reference dataset
D	Calibration & revalidation	Service-time distribution recalibrated using observed utilization; before/after comparison
E	Experimental design	30 matched replications comparing 1 vs. 2 consultation officers (common random numbers)
F	Sensitivity & credibility	Demand sensitivity analysis (±20%), full V&V audit trail, final validation conclusion
Key findings
The baseline stochastic model failed validation (±10% acceptance criterion): mean waiting time was overestimated by +111.9% and utilization by +13.4%.
Calibrating the service-time distribution (mode 4→3 min, max 8→6 min, based on observed utilization) brought utilization within tolerance and matched observed maximum queue length almost exactly, though mean waiting time still underestimates by ~32% — reported as an honest, unresolved limitation.
Under the calibrated model, adding a second officer reduced mean waiting time by ~93%, a statistically robust result (non-overlapping 95% confidence intervals across 30 matched replications).
Sensitivity analysis showed the one-officer system operates close to saturation: a 20% increase in demand nearly tripled mean waiting time.
Files
├── week2_lab.py                          # Main notebook/script (Parts A–F)
├── CCS3209_Week2_Lab_Report.docx          # Full laboratory report
├── stochastic_baseline_20reps.csv         # Part C: 20 baseline replications
├── part_d_calibration_comparison.csv      # Part D: original vs. calibrated replications
├── part_e_scenario_comparison.csv         # Part E: 1-officer vs. 2-officer replications
├── part_f_sensitivity_analysis.csv        # Part F: demand sensitivity results
└── README.md
Requirements
Python 3.x
numpy
matplotlib (for plots)
scipy (Part E confidence intervals)

No pandas dependency — CSV files are written using Python's built-in csv module.

Running

Open week2_lab.py in PyCharm (or any Jupyter-compatible environment, given the #%% cell markers) and run cells top to bottom. A fixed random seed is used throughout each part for reproducibility.
