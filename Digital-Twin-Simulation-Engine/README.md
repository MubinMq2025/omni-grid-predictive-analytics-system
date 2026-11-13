# Digital Twin & Simulation Engine

A **hybrid physics-informed ML digital twin** that simulates inverter electrical and thermal behaviour, then runs what-if scenarios at plant level.

## Problem
Testing heatwaves, soiling or maintenance strategies on real assets is costly and risky. A virtual replica allows safe scenario testing and provides an environment for training future RL agents.

## Approach
1. **Component-level twin:** ML models predict efficiency, internal temperature, reactive power, voltage ripple, harmonic distortion, insulation resistance and fan speed.
2. **Plant-level simulation:** aggregates component predictions into energy, thermal risk and power-quality KPIs.
3. **What-if scenarios:** heatwave, dust and soiling, power-quality disturbance, preventive maintenance and combined stress.
4. **Synthetic failure injection:** flags thermal, power-quality, insulation and control stress patterns.

## Results
| Twin target | R² | MAPE |
|---|---|---|
| Efficiency | 0.93 | 0.46% |
| Insulation resistance | 0.89 | 2.7% |
| Voltage ripple | 0.88 | 9.8% |
| Harmonic distortion | 0.86 | 10.1% |

| Scenario | Energy change vs baseline | High-risk records |
|---|---|---|
| Preventive maintenance | **+2.5%** | 5 (from 8) |
| Dust and soiling | -3.3% | 8 |
| Combined stress | -3.5% | 16 |

Internal temperature and fan speed are harder to model (R² around 0.25), which is noted as a next step.

## Tech
Python, pandas, scikit-learn, joblib, Matplotlib

## Files
| File | Description |
|---|---|
| `digital_twin_simulation_prototype.ipynb` | Full prototype notebook |
| `Digital_Twin_Simulation_Engine_Design.pdf` | Design document |
| `outputs/` | Twin metrics, scenario results, fault injection summary |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
