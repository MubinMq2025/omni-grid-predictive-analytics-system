# AI-Driven Maintenance Scheduling Optimizer

Turns inverter health telemetry into a **constraint-aware maintenance schedule** that ranks assets by risk and assigns crews, skills and parts to minimise total cost.

## Problem
Maintenance teams have limited crews and parts. Fixing assets in the wrong order increases downtime cost and emergency callouts.

## Approach
1. Converted daily inverter time-series records into a latest asset-level planning snapshot.
2. Engineered risk, urgency, anomaly, criticality, spare-parts availability and feasibility scores.
3. Combined them into a single **maintenance priority score** per inverter.
4. Built a **greedy constraint-aware scheduler** that respects crew capacity, required skills and part availability.
5. Compared scheduling cost against a simple first-come baseline.

## Results
| Metric | Value |
|---|---|
| Tasks scheduled | 39 |
| Baseline estimated cost | $551,230 |
| Optimised estimated cost | $492,464 |
| **Cost reduction** | **10.66%** |

## Tech
Python, pandas, NumPy, Matplotlib

## Files
| File | Description |
|---|---|
| `maintenance_scheduling_prototype.ipynb` | Full prototype notebook |
| `Maintenance_Scheduling_Design.pdf` | Design document |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
