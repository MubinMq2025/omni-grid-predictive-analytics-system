# DER Orchestration & Dispatch Optimization

Optimises **solar and battery dispatch** across distributed energy resources (DER) to maximise revenue while keeping the grid within safe limits.

## Problem
Operators must decide every interval how much energy to store, discharge, export or curtail. Simple rules leave revenue on the table, while full optimisation is too slow for real-time decisions.

## Approach
1. Built dispatch-focused features from inverter telemetry and a controlled synthetic market and battery layer.
2. Created a rule-based **baseline dispatch policy**.
3. Built an **MPC-style optimiser** for charge, discharge, export and curtailment decisions.
4. Trained an **ML policy model** that imitates the optimiser so decisions can be made instantly.
5. Added a **real-time adjustment classifier** and evaluated business impact.

## Results (test period)
| Metric | Baseline | Optimiser | ML Policy |
|---|---|---|---|
| Revenue (AUD) | $665,308 | $724,188 | $723,337 |
| Uplift vs baseline | | **+8.85%** | **+8.72%** |
| Grid export (MWh) | 8,389 | 9,022 | 9,014 |
| Grid violations | | 0 | 0 |

The ML policy reproduces the optimiser with R² between 0.97 and 0.999 across dispatch targets.

## Tech
Python, pandas, scikit-learn, joblib, Matplotlib

## Files
| File | Description |
|---|---|
| `der_dispatch_optimization_prototype.ipynb` | Full prototype notebook |
| `DER_Dispatch_Optimization_Design.pdf` | Design document |
| `outputs/` | Business impact and model metrics |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
