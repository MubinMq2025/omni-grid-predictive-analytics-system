# Supply Chain & Spare Parts Optimization

Uses predictive maintenance signals to **forecast spare-parts demand** and generate budget-aware procurement recommendations with safety stock and reorder points.

## Problem
Holding too much stock ties up cash, while too little causes long outages when a critical part fails. Demand for parts is driven by asset health, which traditional inventory planning ignores.

## Approach
1. Mapped inverter health and failure-risk signals to component-level spare-parts demand.
2. Built monthly demand records and trained a **demand forecasting model**.
3. Trained a **supplier delay risk classifier**.
4. Calculated **safety stock, reorder points and order-up-to levels**.
5. Applied budget-aware procurement allocation and compared against a baseline policy.

## Results
| Metric | Value |
|---|---|
| Risk-adjusted operational cost reduction | **73.8%** vs baseline |
| Total recommended order cost | $233,820 |
| Output | Prioritised order list by part, site and supplier |

## Tech
Python, pandas, NumPy, scikit-learn, Matplotlib

## Files
| File | Description |
|---|---|
| `spare_parts_optimization_prototype.ipynb` | Full prototype notebook |
| `Spare_Parts_Optimization_Design.pdf` | Design proposal |
| `outputs/` | Procurement recommendations, monthly training data |
| `data/` | Sample data and data dictionary |

## Note on Data
All data is synthetic and generated for prototyping. Only a sample file and the data dictionary are included here to keep the repository lightweight. The notebook was run on the full synthetic dataset (about 9 MB), which can be regenerated or requested.

[Back to main README](../README.md)
