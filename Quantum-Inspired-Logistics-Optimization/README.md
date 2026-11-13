# Quantum-Inspired Logistics Optimization

Converts asset failure risk into **maintenance logistics decisions**: which jobs to dispatch, which crew takes them, and the best route, using a quantum-inspired simulated annealing optimiser.

## Problem
Field crews waste time and fuel on inefficient routes and miss service windows for high-risk assets. Vehicle routing with skills, time windows and parts is a hard combinatorial problem.

## Approach
1. Trained a **failure risk classifier** on inverter telemetry to generate maintenance demand.
2. Simulated logistics attributes (depots, coordinates, crew capacity, skills, time windows, parts).
3. Built a baseline routing plan.
4. Improved it with a **quantum-inspired simulated annealing optimiser** (classical algorithm inspired by quantum annealing).
5. Produced optimised crew schedules, route maps, KPI comparison and a spare-parts reorder plan.

## Results
| Metric | Value |
|---|---|
| Failure risk model ROC-AUC | 0.998 |
| Optimisation objective improvement | **13.6%** |
| Route distance reduction | **22.1%** (731 km to 569 km) |
| Lateness reduction | **27.9%** |

## Tech
Python, pandas, NumPy, scikit-learn, Matplotlib

## Files
| File | Description |
|---|---|
| `quantum_inspired_logistics_prototype.ipynb` | Full prototype notebook |
| `Quantum_Inspired_Logistics_Design.pdf` | Design document |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
