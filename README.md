# MSIN0097 Predictive Analytics — Individual Coursework
## UK Road Safety: Predicting Collision Severity

**Module:** MSIN0097 Predictive Analytics  
**Student ID:** 25229477  
**Dataset:** UK STATS19 Road Safety Data, 2024  
**Task:** Binary classification — predict whether a road collision results in serious/fatal injury  

---

## Project Overview

This project builds an end-to-end machine learning pipeline to predict road collision severity using the UK Department for Transport STATS19 2024 dataset. Given conditions known at the time of a collision (road type, speed limit, vehicle type, weather, time of day etc.), the model predicts whether the outcome will be serious/fatal (1) or slight (0).

**Final model:** XGBoost (GridSearchCV tuned)  
**Test AUC-ROC:** 0.6983  
**Test Recall:** 0.6378 (catches ~64% of serious/fatal collisions)

---

## Repository Structure

```
Predictive-Analytics-MSIN0097/
│
├── MSIN0097_Predictive_Analytics_AKS.ipynb   ← main notebook (all 6 steps)
├── requirements.txt                           ← Python dependencies
├── README.md                                  ← this file
└── data/
    └── data_access.md                         ← instructions for downloading data
```

---

## Data Access

The data used in this project is publicly available from the UK Department for Transport:

1. Go to: https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-safety-data
2. Download the following files for 2024:
   - `dft-road-casualty-statistics-collision-2024.csv`
   - `dft-road-casualty-statistics-vehicle-2024.csv`
   - `dft-road-casualty-statistics-road-safety-open-dataset-data-guide-2024.xlsx`
3. Place all three files in a folder and update the `BASE_PATH` and `DATA_PATH` variables at the top of Step 2 in the notebook to point to your local directory.

**Licence:** Open Government Licence v3.0

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/ash54uk/Predictive-Analytics-MSIN0097.git
cd Predictive-Analytics-MSIN0097
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Download the data

Follow the instructions in the **Data Access** section above.

### 5. Run the notebook

```bash
jupyter notebook MSIN0097_Predictive_Analytics_AKS.ipynb
```

Run all cells in order from top to bottom using **Kernel → Restart & Run All**.

---

## Notebook Structure

The notebook follows the six-step ML workflow required by the assignment brief:

| Step | Description |
|------|-------------|
| Step 1 | Problem framing — define target, metrics, assumptions |
| Step 2 | EDA — distributions, missingness, class imbalance, leakage risks |
| Step 3 | Data preparation — feature engineering, pipeline, train/val/test split |
| Step 4 | Model exploration — Logistic Regression, Decision Tree, Random Forest, XGBoost, LightGBM, Neural Network (MLP) |
| Step 5 | Fine-tuning and evaluation — RandomizedSearchCV, GridSearchCV, SHAP values, error analysis |
| Step 6 | Final solution — model card, limitations, risks, next steps |

---

## Results Summary

| Model | AUC-ROC | F1 | Precision | Recall |
|---|---|---|---|---|
| Logistic Regression | 0.6815 | 0.4551 | 0.3492 | 0.6534 |
| Decision Tree | 0.6627 | 0.4457 | 0.3307 | 0.6833 |
| Random Forest | 0.6932 | 0.4532 | 0.3853 | 0.5501 |
| XGBoost | 0.7045 | 0.4770 | 0.3741 | 0.6582 |
| LightGBM | 0.7058 | 0.4748 | 0.3694 | 0.6641 |
| Neural Network (MLP) | 0.6196 | 0.3665 | 0.3410 | 0.3961 |
| **XGBoost (tuned)** | **0.6983** | **0.4682** | **0.3699** | **0.6378** |

*Final model evaluated on held-out test set. All other results on validation set.*

---

## Agent Tooling

This project was developed using **Claude Sonnet 4.6** (Anthropic, 2025) as an agent collaborator for:
- Scaffolding code structure and pipelines
- Debugging preprocessing errors
- Generating visualisations
- Drafting documentation

All agent contributions were verified before being incorporated. Errors caught during development are documented in the **Agent Usage Log** appendix of the submitted report.

---

## Requirements

See `requirements.txt` for the full dependency list. Key libraries:

- `scikit-learn==1.6.1`
- `xgboost==3.2.0`
- `lightgbm==4.6.0`
- `shap==0.51.0`
- `pandas==2.2.3`

Python 3.11+ recommended.

---

## License

This project is submitted for academic assessment at UCL. Data is used under Open Government Licence v3.0.
