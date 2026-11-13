# Automated Remote Fixing & Self-Healing

Diagnoses inverter faults, recommends **safe remote remediation actions**, and passes every action through a safety gate with rollback logic and a full audit trail.

## Problem
Many inverter faults can be fixed remotely (reset, recalibration), but unsafe automated actions on live energy assets carry real risk. The system has to know when to act and when to escalate to a human.

## Approach
1. Generated fault signatures from telemetry patterns (temperature, efficiency, insulation, restarts, errors).
2. Trained a **fault diagnosis classifier** and a **7-day failure risk model** (scikit-learn).
3. Mapped diagnoses to actions with a **rule-based remediation policy**.
4. Applied a **safety gate** that blocks high-risk actions and routes them for human approval.
5. Simulated rollback behaviour and generated an auditable action log.

A reinforcement learning agent is the long-term design, but the data has no historical action outcomes, so this prototype uses ML plus expert rules. That is the safer and more honest choice at this stage.

## Results
| Metric | Value |
|---|---|
| Fault diagnosis accuracy | 98.45% |
| 7-day failure risk accuracy | 99.31% |
| 7-day failure risk ROC-AUC | 0.999 |
| Actions eligible for auto-execution | 52.1% |
| Actions blocked by safety gate | 47.9% |
| Simulated rollbacks triggered | 0.02% |

## Tech
Python, pandas, scikit-learn, joblib, Matplotlib

## Files
| File | Description |
|---|---|
| `remote_fixing_self_healing_prototype.ipynb` | Full prototype notebook |
| `Remote_Fixing_Self_Healing_Design.pdf` | Design document |
| `outputs/` | KPI summary, action summary, feature importance |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
