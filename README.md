# Network Anomaly Detector

A machine learning project for detecting anomalous network traffic using Random Forest and XGBoost on the CICIDS2017 dataset.

## Overview
This project applies supervised machine learning to detect malicious traffic in network logs. It demonstrates data cleaning, feature engineering, pipeline building, model tuning, and evaluation. This repository is structured for clarity and reproducibility, suitable for academic, portfolio, or internship purposes.

## Project Structure
```
├── data/                # Raw and cleaned datasets (not committed)
├── models/              # Models created throughout the anomaly detectors development
├── notebooks/           # EDA and model development
├── src/                 # Modular code (e.g. preprocessing, training)
├── results/             # Evaluation plots and reports
├── requirements.txt     # Dependencies
└── README.md
```

---

## Progress Overview

| Day | Focus | Status |
|-----|-------|--------|
| 1–2 | Data ingestion, EDA, preprocessing | Completed |
| 3–4 | Baseline models (Logistic Regression, Random Forest) | Completed |
| 5 | XGBoost, leakage prevention checks | Completed |
| 6 | Autoencoder for anomaly detection | Completed |
| 7 | Hybrid model (Autoencoder + XGBoost) | Completed |
| 8–14 | Advanced evaluation, explainability, deployment | In progress |

---

## Models Developed So Far

- **Baseline Supervised Classifiers**
  - Logistic Regression
  - Random Forest
  - XGBoost (after leakage correction)

- **Unsupervised Anomaly Detection**
  - Deep Autoencoder trained on benign traffic only

- **Hybrid Detector (Current Best Model)**
  - Autoencoder reconstruction error added as a feature
  - Trained using leakage-safe day-based split  
    (Mon–Thu for training, Fri for initial testing)

---

## Key Results (as of Day 7)

| Model | Evaluation Strategy | Accuracy | ROC-AUC | Notes |
|-------|--------------------|---------:|-------:|------|
| XGBoost baseline | Mixed-day test | ~0.84–0.99 | ~0.85–1.00 | Sensitive to leakage |
| Autoencoder only | Reconstruction threshold | ~0.65 | ~0.68 | Detects anomalies but weak precision |
| Hybrid AE + XGB | Friday Afternoon attacks | ~0.99+ | ~0.99+ | Good generalization to seen attack families |

These results reflect detection of attack patterns that are similar to training data.  
Zero-day evaluation is planned next.

---

## Next Steps

- Day 8: Zero-day attack generalization (hold-out attack type testing)
- Day 9: Threshold tuning + Precision/Recall optimization
- Day 10: Explainability (SHAP, feature importance)
- Day 11: Model persistence and deployment formats
- Day 12: Real-time streaming inference test
- Day 13: Dashboard and visualization
- Day 14: Final documentation + portfolio packaging

---

## Requirements

- Python 3.10+
- TensorFlow 2.x (GPU recommended)
- XGBoost
- Scikit-learn
- Matplotlib / Seaborn

See `requirements.txt` for full list.

---

## Author

This project is actively developed as a machine learning and cybersecurity study focused on real-world anomaly detection challenges.

## Features
- Pipelines with preprocessing
- Cross-validation & hyperparameter tuning
- ROC curves, confusion matrices, F1 scores
- Data leakage checks

## Models
- Random Forest
- XGBoost
- Tensorflow

## Dataset
- [CICIDS 2017](https://www.unb.ca/cic/datasets/ids-2017.html)
- Alternatively, [KDD Cup 99](https://www.kaggle.com/datasets/galaxyh/kdd-cup-1999-data)

