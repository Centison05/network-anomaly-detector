# 🛰️ Network Anomaly Detector

A machine learning project for detecting anomalous network traffic using Random Forest and XGBoost on the CICIDS2017 dataset.

## 📌 Overview
This project applies supervised machine learning to detect malicious traffic in network logs. It demonstrates data cleaning, feature engineering, pipeline building, model tuning, and evaluation. This repository is structured for clarity and reproducibility, suitable for academic, portfolio, or internship purposes.

## 📂 Project Structure
```
├── data/                # Raw and cleaned datasets (not committed)
├── notebooks/           # EDA and model development
├── src/                 # Modular code (e.g. preprocessing, training)
├── results/             # Evaluation plots and reports
├── requirements.txt     # Dependencies
└── README.md
```

## 🧠 Features
- Pipelines with preprocessing
- Cross-validation & hyperparameter tuning
- ROC curves, confusion matrices, F1 scores
- Data leakage checks

## 🧪 Models
- Random Forest
- XGBoost

## 📊 Dataset
- [CICIDS 2017](https://www.unb.ca/cic/datasets/ids-2017.html)
- Alternatively, [KDD Cup 99](https://www.kaggle.com/datasets/galaxyh/kdd-cup-1999-data)

## 🚀 Next Steps
- Try deep learning models
- Deploy via Flask or FastAPI
