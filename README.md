# Shell.ai 6th Edition — Fuel Blend Property Prediction

Predicting the properties of fuel blends formed by mixing sustainable and conventional components.

- Challenge: predict 10 target blend properties from component fractions and per-component properties
- Goal: help industry rapidly evaluate and optimize fuel blends for safety, performance, sustainability, and cost-efficiency
- Evaluation metric: MAPE (Mean Absolute Percentage Error)

---

## Repository Structure

- `dataset/`
  - `train.csv` — training data with features and target columns
  - `test.csv` — test data with an `ID` column and features (no targets)
- `result/`
  - `submission_catboost.csv` — sample submission with predictions for 10 targets
  - `plots/`
    - `Actuals vs Predicted.png`
    - `residuals.png`
- `BlendProperty.ipynb` — notebook for exploration/modeling
- `requirements.txt` — Python dependencies

---

## Data Schema

Each row represents a fuel blend composed of 5 components.

- Features (55 total):
  - Fractions: `Component{1..5}_fraction` (5 cols)
  - Per-component properties: `Component{1..5}_Property{1..10}` (5 × 10 = 50 cols)
- Targets (10 total, train only): `BlendProperty{1..10}`
- Test-only ID: `ID`

Example (columns abbreviated):
```
Component1_fraction, ..., Component5_fraction,
Component1_Property1, ..., Component5_Property10,
[BlendProperty1, ..., BlendProperty10]  # train only
```

---

## Environment Setup

- Python 3.x
- Install dependencies:

```bash
pip install -r requirements.txt
```

Dependencies (from `requirements.txt`):
- pandas, scikit-learn, matplotlib
- catboost, xgboost, lightgbm

---

## Modeling and Evaluation

- Primary metric: MAPE
  - MAPE = mean(|(y_true − y_pred) / y_true|) × 100%
- Multi-target regression: predict `BlendProperty1..10` simultaneously or independently.
- This repo includes a CatBoost-based submission (`result/submission_catboost.csv`). Other gradient boosting models (XGBoost/LightGBM) and linear baselines can be used as alternatives.

Plots (from a sample model fit):

- Actual vs Predicted
  
  ![Actuals vs Predicted](result/plots/Actuals%20vs%20Predicted.png)

- Residuals
  
  ![Residuals](result/plots/residuals.png)

---

## Quick Start

1. Place data in `dataset/` with the exact filenames:
   - `dataset/train.csv`
   - `dataset/test.csv`
2. Create and activate a virtual environment (optional) and install requirements:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `BlendProperty.ipynb` to explore, train, and generate predictions.
4. Save predictions in the submission format (see below) to `result/submission_<model>.csv`.

---

## Submission Format

CSV with the following columns (header required):

```
ID,BlendProperty1,BlendProperty2,BlendProperty3,BlendProperty4,BlendProperty5,BlendProperty6,BlendProperty7,BlendProperty8,BlendProperty9,BlendProperty10
```

An example file is provided at `result/submission_catboost.csv`.

## Acknowledgments

This project was developed for the Shell.ai Hackathon (6th year edition)

---

