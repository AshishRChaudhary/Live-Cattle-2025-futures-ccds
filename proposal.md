## 1. Project Overview and goal

This project applies supervised machine learning to daily OHLCV and Open Interest data from six Live Cattle (LE) CME futures contracts expiring across 2025. The goal is to build a trade signal classifier that predicts one of three forward-looking states — **Buy**, **Sell**, or **Hold** — for each trading day.

## 2. Data Summary

All input data is sourced from Barchart historical exports. Each of the 6 contract files contains approximately 376–380 rows of daily OHLCV + Open Interest data.

| Contract | Expiry   | Date Range              | Rows | Close Range             |
|----------|----------|-------------------------|------|-------------------------|
| LEG25    | Feb 2025 | Aug 2023 – Feb 2025     | 376  | $175.35 – $208.55       |
| LEJ25    | Apr 2025 | Oct 2023 – Apr 2025     | 376  | $176.85 – $216.35       |
| LEM25    | Jun 2025 | Dec 2023 – Jun 2025     | 376  | $171.48 – $228.20       |
| LEQ25    | Aug 2025 | Feb 2024 – Aug 2025     | 378  | $169.68 – $243.25       |
| LEV25    | Oct 2025 | Apr 2024 – Oct 2025     | 380  | $171.38 – $243.95       |
| LEZ25    | Dec 2025 | Jun 2024 – Dec 2025     | 377  | $173.08 – $247.88       |

---

## 3. Objectives

- Construct a clean, unified daily price series from all 6 contracts
- Engineer predictive features from OHLCV and Open Interest data
- Label each row with a forward-looking trade signal: Buy / Sell / Hold
- Train, validate, and compare classifiers (Random Forest, XGBoost, LSTM)
- Evaluate model performance using F1, precision, and recall per class
- Document all steps reproducibly in Jupyter notebooks committed to GitHub

---

## 4. Repository Structure

```
le25-ml-signals/
├── README.md
├── .gitignore
├── requirements.txt
├── data/
│   └── raw_files/                      
├── notebooks/
│   ├── 01_data_prep.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_labeling.ipynb
│   ├── 05_modeling.ipynb
│   └── 06_evaluation.ipynb
├── src/
│   ├── loader.py
│   ├── features.py
│   ├── labels.py
│   └── models.py
└── outputs/                   
```


## Summary

This proposal defines a complete end-to-end ML pipeline for LE25 futures trade signal classification, a phased notebook layout that separates data, features, modeling, and evaluation into reviewable, mergeable units.
