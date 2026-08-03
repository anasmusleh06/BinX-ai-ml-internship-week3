# Linear Regression

#### Week 3 - Day 2

## Overview:

This notebook covers the fundamentals of **Linear Regression**, the first predictive model built in Phase 2 of the internship. The goal is to train a model that predicts a continuous numeric value (house price), interpret how it makes its predictions and evaluate its performance using standard regression metrics.


## Learning Objectives:

- In this notebook, we will cover:

1. Train a LinearRegression model on a provided regression dataset (I used California housing).
2. Report the model's coefficients and identify which feature has the strongest effect.
3. Evaluate the model with MAE, RMSE, and R² on the test set.
4. Compare the RMSE against a baseline that predicts the mean for every row, and state whether the model adds value.
5. Document the interpretation of results in Markdown.
> Note: Words written in bold represents key topics that were studied and covered during the day.

## Dataset:

- **California Housing Dataset** (loaded via sklearn.datasets.fetch_california_housing)

| Detail | Description |
|---|---|
| Samples | 20,640 rows |
| Features | 8 numeric features (e.g. median income, house age, average rooms, population, location) |
| Target | "MedHouseVal" — median house value (in $100,000s) for California districts |
| Task Type | Regression (predicting a continuous number) |


## Methodology:

- The notebook follows this pipeline:

1. **Load Data** — Import the California Housing dataset into a pandas DataFrame.
2. **Feature/Target Split** — Separate the data into "X" (features) and "y" (target).
3. **Train/Test Split** — 80/20 split with "random_state=42" for reproducibility.
4. **Model Training** — Fit a "LinearRegression" model on the training set.
5. **Prediction** — Generate predictions on the held-out test set.
6. **Interpretation** — Extract and rank feature coefficients to identify the strongest predictors.
7. **Evaluation** — Compute MAE, RMSE, and R² on the test set.
8. **Baseline Comparison** — Compare model RMSE against a baseline that always predicts the mean.

## Results:

| Metric | Value |
|---|---|
| MAE | (0.5332) |
| RMSE | (0.7456) |
| R² | (0.5758) |
| Baseline RMSE | (1.1449) |

**Strongest predictive feature:** (MedInc)

## Tools Used:

- **Scikit-learn** (LinearRegression, train_test_split and metrics).
- **Pandas** — data loading and manipulation.
- **NumPy** — numerical operations (e.g. RMSE calculation).
- **Jupyter Notebook** — development environment.