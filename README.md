# zomathon-kpt-optimization
Signal de-biasing and rush modeling framework to improve Kitchen Prep Time (KPT) prediction, reducing ETA MAE by ~18% in Zomathon 2026.

# KPT Signal Debiasing & Rush Modeling Framework
Zomathon 2026 | Problem Statement 1  
Team: DataShakti

---

## Overview

This project proposes a signal de-biasing and rush modeling framework to improve Kitchen Prep Time (KPT) prediction in food delivery operations.

Our approach focuses on improving signal quality before model training by:

- Correcting systematic merchant FOR bias
- Applying historical smoothing
- Modeling real-time rush intensity
- Introducing reliability-weighted signal adjustment

The framework achieves measurable ETA error reduction while remaining scalable and model-agnostic.

---

## Key Results

| Metric | Baseline | Improved (RF Model) |
|--------|----------|---------------------|
| MAE | 3.01 min | 2.46 min |
| Improvement | — | ~18% |
| Error Reduction | — | ~0.6 min/order |

Estimated rider time saved at 100K daily orders:
~930 rider hours/day

---

## System Architecture

1. Raw Signal Intake  
2. Historical Smoothing (EWMA)  
3. Merchant Bias Estimation  
4. Reliability Score Calculation  
5. Rush Index Modeling (Rolling 15-min Window)  
6. Adjusted Feature Engineering  
7. Model Training (Random Forest)  
8. Evaluation & Impact Simulation  

---

## Dataset

- Self-curated dataset (~30K orders)
- Includes:
  - Actual prep time
  - Observed prep time
  - Rider wait time
  - Order hour & day of week
  - Rush intensity score
  - Merchant bias signals

All data preparation steps are documented in the notebook.

---

## Model & Evaluation

Baseline:
- Direct use of observed merchant-marked prep time

Improved Model:
- Random Forest Regressor
- Debiased & rush-aware features
- Reliability-weighted adjustments

Evaluation Metrics:
- MAE
- P50 Error
- P90 Error

---

## Business Impact

- Reduced ETA prediction error  
- Reduced early rider arrival  
- Improved fleet utilization  
- Scalable across 300K+ merchants  
- No additional hardware required  

---

## Scalability

- Uses rolling aggregations
- Works with any regression model
- Merchant-agnostic
- Production-ready monitoring via BI dashboard

---

## Dashboard

Power BI dashboard used for:
- Operational monitoring
- City-level impact tracking
- Error distribution comparison
- Merchant-level analysis

---

## Resources

- Dataset: https://drive.google.com/file/d/1nPG2fsD0uNQnpDbUzXGaFwrbNr1d6Vok/view?usp=sharing
- Notebook: https://drive.google.com/file/d/1WepykT0XHvggRwUZbCXoPscuBU9CTTnF/view?usp=sharing
- Dashboard: https://drive.google.com/file/d/1ffCnj-dTgu8z72Rx4zs1vhX8Qc35xA3m/view?usp=sharing  (Use Powerbi)
- Document: https://drive.google.com/file/d/1EoI7AtvMwYRygPEOivOW70kfcF-r8ljG/view?usp=drive_link
(All links are set to public access for evaluation purposes.)

---

## Note

This solution was developed for Zomathon 2026.  
The problem statement is confidential and not publicly shared.

---

## Team

DataShakti  
Zomathon 2026
