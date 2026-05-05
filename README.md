# Machine Learning Assignment

A three-part machine learning assignment covering k-NN classification, PCA dimensionality reduction, and Singular Value Decomposition (SVD).

---
## 📁 Repository Structure
 
```
ml-assignment/
│
├── notebooks/
│   └── ML_assignment.ipynb       # Main Jupyter notebook with all code
│
├── report/
│   └── ML_Assignment_Report.pdf  # Full written report
│
├── data/                         # Datasets used in the assignment
│
├── requirements.txt              # Python dependencies
└── README.md
```
 
## 📚 Assignment Overview

### Task 1 — k-Nearest Neighbours (k-NN) Classification
- Applied k-NN to the **Wisconsin Breast Cancer dataset** for binary classification (Benign / Malignant)
- Personalised hyperparameters: **k = 6**, **p = 6** (Minkowski distance)
- **70/30 train/test split** → 398 training samples, 171 test samples
- Computed **P(N | +)** — the probability a truly negative (benign) patient is predicted positive (malignant)
  - Result: **P(N | +) ≈ 0.0741** (7.41% false positive rate)

### Task 2 — Principal Component Analysis (PCA)
- Applied PCA as a preprocessing step before k-NN classification
- Recommended **nc = 3 principal components**, capturing **88.96%** of total variance
- PCA marginally improved performance: **P(N | +)** dropped to **6.48%**, reducing false alarms
- The 2 discarded components (11.04% variance) were considered noise rather than useful signal

### Task 3 — Singular Value Decomposition (SVD)
- Applied SVD to **Amazon stock price data** (Open, High, Low, Close) over 231 trading days
- Analysed pair plots and found all four price variables to be near-perfectly linearly correlated
- Matrix X_train (231×4) is technically **full rank 4** but **effectively rank 1** (σ₁ = 6625.81, 172× larger than σ₂ = 38.54)
- Compared compressed representations Kc (training) and Qc (test) for c = 1 and c = 2
  - **c = 1**: reconstruction error = 51.48 — data collapses to a single line
  - **c = 2**: reconstruction error = 34.13 — second component recovers spread between High and Low

---

## 🛠️ Setup & Usage

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab

---

## 📦 Dependencies

See [`requirements.txt`](requirements.txt) for the full list. Key libraries:

| Library | Purpose |
|---|---|
| `numpy` | Numerical computation |
| `pandas` | Data manipulation |
| `scikit-learn` | k-NN, PCA, train/test split, metrics |
| `matplotlib` | Plotting |
| `seaborn` | Pair plots and visualisations |

---

## 📊 Key Results Summary

| Task | Method | Key Metric |
|---|---|---|
| Task 1 | k-NN (k=6, p=6) | Accuracy on test set, P(N\|+) = 7.41% |
| Task 2 | PCA + k-NN (nc=3) | P(N\|+) = 6.48%, 88.96% variance retained |
| Task 3 | SVD (c=1,2) | Reconstruction error: 51.48 → 34.13 |

---

## 📄 License
This project is submitted for academic assessment. Please do not copy or reproduce for your own submissions.
