# Day 3 — Logistic Regression & Classification Metrics:

#### Week 3 - Day 3

## Overview:

This notebook covers **Day 3** of Week 3 in the BinX Tech AI & ML Internship Program, focused on **Logistic Regression and classification metrics**.
The goal is to move beyond simple accuracy and build a rigorous evaluation workflow for binary classification problems — one that reflects how models are actually assessed in real-world, high-stakes applications such as medical diagnosis.

Unlike Day 2, where the target was a continuous number (regression), Day 3 deals with a **categorical target**: predicting whether a tumor is malignant or benign. This shift requires a different toolkit — confusion matrices, precision, recall, F1-score and AUC-ROC — instead of MAE, RMSE and R².


## Learning Objectives:

By completing this notebook, the following objectives were achieved:

- 1. Train a `LogisticRegression` classifier and generate class probabilities using `predict_proba`.
- 2. Explain why accuracy alone is a misleading metric on imbalanced datasets.
- 3. Read and interpret a confusion matrix (TP, FP, FN, TN).
- 4. Compute and interpret precision, recall, and F1-score using `classification_report`.
- 5. Make and justify a data-driven decision about which metric (precision vs. recall) matters most for a specific real-world problem.
- 6. Compute and interpret AUC-ROC as a threshold-independent performance measure.

## Dataset:

**Breast Cancer Wisconsin (Diagnostic) Dataset** — loaded directly from `sklearn.datasets.load_breast_cancer`,so the notebook is fully reproducible with no external files required.

| Property | Value |
|---|---|
| Samples | 569 |
| Features | 30 numeric features (computed from digitized images of cell nuclei) |
| Target classes | `0 = malignant` (خبيث), `1 = benign` (حميد) |
| Class balance | 212 malignant / 357 benign (moderately imbalanced) |
| Train/test split | 80% / 20%, `random_state=42`, `stratify=y` |

This dataset was intentionally chosen over a generic churn dataset because it maps directly onto the lesson's central discussion point: **in medical screening, the cost of a false negative is far higher than the cost of a false positive** — which makes it an ideal case study for the precision/recall trade-off
covered on Day 3.

## Methodology:

The notebook follows a clean, linear pipeline:

1. **Data loading & inspection** — load the dataset, confirm shapes, and check class balance to flag potential imbalance issues up front.
2. **Train/test split** — an 80/20 split with `stratify=y` to preserve the original class ratio in both subsets, which matters specifically because the data is imbalanced.
3. **Model training** — a `LogisticRegression(max_iter=5000)` model trained only on `X_train, y_train`.
4. **Prediction & confusion matrix** — predictions generated on the untouched test set, then broken down into TP / FP / FN / TN.
5. **Classification report** — precision, recall, and F1-score computed per class via `classification_report`.
6. **Metric decision** — an explicit, justified decision on whether precision or recall should be prioritized for this specific problem.
7. **AUC-ROC** — a threshold-independent evaluation using `roc_auc_score` and a plotted ROC curve.

## Results:

### Classification Report:

| Class | Precision | Recall | F1-score | Support |
|---|---|---|---|---|
| Malignant | 0.97 | 0.91 | 0.94 | 43 |
| Benign | 0.95 | 0.99 | 0.97 | 71 |
| **Accuracy** | | | **0.96** | 114 |
| Macro avg | 0.96 | 0.95 | 0.95 | 114 |
| Weighted avg | 0.96 | 0.96 | 0.96 | 114 |

### Confusion Matrix:

| | Predicted Malignant | Predicted Benign |
|---|---|---|
| **Actual Malignant** | 39 (TP) | 4 (FN) |
| **Actual Benign** | 1 (FP) | 70 (TN) |

### AUC-ROC:

> 0.9977

## Key Insights:

- **Accuracy (0.96) looks excellent on its own, but it hides the real story.** The per-class breakdown is what reveals the model's actual weak point: 4 malignant cases were misclassified as benign.
- **Recall for the malignant class (0.91) is the single most important number in this notebook.** It means the model missed 4 out of 43 true cancer cases — a number that matters far more in a clinical context than the overall accuracy figure.
- **Precision for the malignant class (0.97) is strong**, meaning the model rarely raises a false alarm when it does flag a tumor as malignant.
- **F1-score (0.94)** offers a single balanced number, but a balanced number is not always what a high-stakes problem needs — sometimes one metric deserves more weight than the other, and that decision has to be justified explicitly rather than defaulting to F1.

## Clinical Relevance: Why Recall Matters Here:

This is the core analytical decision of the notebook: **for this specific problem, recall is prioritized over precision.**

- A **False Negative** (predicting "benign" when the tumor is actually malignant) means a patient goes undiagnosed and untreated — a severe, potentially irreversible outcome.
- A **False Positive** (predicting "malignant" when the tumor is benign) leads to additional testing and temporary patient anxiety — an inconvenience, but not a comparable harm.

Given this asymmetry in consequences, a model that trades a small amount of precision for a meaningful gain
in recall is preferable in this domain — even though it is not the mathematically "balanced" choice. This
mirrors the same precision/recall trade-off principle from the Day 3 lesson: disease screening prioritizes
recall, while a spam filter prioritizes precision.