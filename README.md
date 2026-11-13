# Omni-Grid Predictive Analytics System

An end-to-end **AI platform for renewable energy operations**, made up of 11 machine learning and optimisation modules covering forecasting, asset health, maintenance, grid dispatch, cyber-physical security and supply chain.

Built during my AI/ML Data Analyst internship, using fully synthetic data.

---

## Overview

Renewable energy operators face connected problems: predicting generation, spotting faults early, planning maintenance with limited crews, dispatching energy for maximum revenue and keeping critical spare parts in stock. These are usually solved in separate tools.

Omni-Grid treats them as **one system**. Each module solves one business problem, and the outputs of one feed the next. For example, failure risk drives maintenance scheduling, which drives crew routing and spare-parts ordering.

---

## Modules

| # | Module | What it does | Key techniques | Headline result |
|---|---|---|---|---|
| 1 | [Solar Generation Forecasting](Solar-Generation-Forecasting/) | Forecasts solar energy output | TFT, XGBoost, time-series features | RMSE 37% below the persistence baseline, R² 0.97 |
| 2 | [Anomaly Detection](Anomaly-Detection/) | Flags abnormal inverter behaviour | Isolation Forest, statistical thresholds | ROC-AUC 0.98, 100% recall 7 days ahead |
| 3 | [Predictive Maintenance (RUL)](Predictive-Maintenance/) | Estimates remaining useful life | Gradient Boosting regression | RUL MAE 6.1 days |
| 4 | [Panel Degradation](Panel-Degradation/) | Tracks long-term panel degradation | Regression, trend analysis | R² 0.71, severity F1 0.80 |
| 5 | [Maintenance Scheduling Optimizer](Maintenance-Scheduling-Optimizer/) | Builds a constraint-aware maintenance schedule | Priority scoring, greedy scheduling | **10.7% cost reduction** |
| 6 | [Remote Fixing & Self-Healing](Remote-Fixing-Self-Healing/) | Recommends safe remote fixes with a safety gate | Classification, rule engine, rollback logic | **98.5% fault diagnosis accuracy** |
| 7 | [Cyber-Physical Threat Detection](Cyber-Physical-Threat-Detection/) | Detects suspicious physical-process behaviour | Random Forest, Extra Trees, Isolation Forest | **ROC-AUC 0.99** |
| 8 | [DER Dispatch Optimization](DER-Dispatch-Optimization/) | Optimises solar and battery dispatch | MPC-style optimiser, ML policy imitation | **+8.8% revenue**, 0 grid violations |
| 9 | [Digital Twin & Simulation Engine](Digital-Twin-Simulation-Engine/) | Simulates assets and what-if scenarios | Physics-informed ML, scenario simulation | **R² 0.93** on efficiency |
| 10 | [Quantum-Inspired Logistics](Quantum-Inspired-Logistics-Optimization/) | Optimises crew routing for maintenance jobs | Simulated annealing, vehicle routing | **22% shorter routes** |
| 11 | [Spare Parts Optimization](Spare-Parts-Optimization/) | Forecasts parts demand and plans orders | Demand forecasting, safety stock, reorder points | **73.8% lower risk-adjusted cost** |

Each module folder has its own README with the problem, approach, results and files.

---

## System Architecture

```text
             Synthetic inverter telemetry + weather + operations data
                                     |
         +---------------------------+---------------------------+
         |                           |                           |
   Forecasting                 Asset Health                 Security
   (1) Solar forecast          (2) Anomaly detection        (7) Cyber-physical
                               (3) RUL prediction               threat detection
                               (4) Panel degradation
                               (9) Digital twin
         |                           |                           |
         +---------------------------+---------------------------+
                                     |
                              Decision Layer
           (5) Maintenance scheduling   (6) Remote fixing & self-healing
           (8) DER dispatch              (10) Logistics routing
           (11) Spare parts optimisation
                                     |
              Schedules, dispatch plans, alerts, purchase orders
```

---

## Tech Stack

- **Languages:** Python
- **Data:** pandas, NumPy
- **Machine learning:** scikit-learn, XGBoost, Gradient Boosting, Random Forest, Extra Trees, Isolation Forest, Temporal Fusion Transformer
- **Optimisation:** MPC-style optimisation, simulated annealing, greedy constraint scheduling, inventory optimisation
- **Visualisation:** Matplotlib
- **Tooling:** Jupyter, joblib

---

## Repository Structure

```text
omni-grid-predictive-analytics-system/
├── Solar-Generation-Forecasting/
├── Anomaly-Detection/
├── Predictive-Maintenance/
├── Panel-Degradation/
├── Maintenance-Scheduling-Optimizer/
├── Remote-Fixing-Self-Healing/
├── Cyber-Physical-Threat-Detection/
├── DER-Dispatch-Optimization/
├── Digital-Twin-Simulation-Engine/
├── Quantum-Inspired-Logistics-Optimization/
├── Spare-Parts-Optimization/
├── requirements.txt
└── README.md
```

Each module typically contains a prototype notebook, a design document (PDF), a `data/` folder with sample data and a data dictionary, and an `outputs/` folder with results.

---

## Getting Started

```bash
git clone https://github.com/MubinMq2025/omni-grid-predictive-analytics-system.git
cd omni-grid-predictive-analytics-system
pip install -r requirements.txt
jupyter notebook
```

Open any module's notebook to explore it.

---

## Note on Data

All datasets are **synthetic**, generated to mirror real renewable energy operations without using any confidential data. Where a dataset lacked fields a module needed (for example market prices or depot locations), the notebook documents the assumption and builds a transparent synthetic layer, with notes on what real data would replace it in production.

---

## Key Learnings

- Designing a multi-module ML platform where outputs from one model feed decisions in another
- Combining machine learning with optimisation and rule-based safety logic
- Being honest about data limitations and designing prototypes that can be upgraded with real data
- Translating model metrics into business outcomes such as cost, revenue and downtime

---

## Author

**Kazi Abdul Mubin**
Master of Data Science, Macquarie University

- [LinkedIn](https://www.linkedin.com/in/kazi-abdul-mubin-919041280/)
- [GitHub](https://github.com/MubinMq2025)
