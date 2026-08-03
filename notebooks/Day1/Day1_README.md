# Supervised Learning Concepts & the Scikit-learn API 

**Week 3 - Day 1** — Duration: 8 hours

---

## 🎯 Learning Objectives

By the end of this day, the following objectives were achieved:

- Explain what supervised learning is and distinguish regression from classification.
- Separate a dataset into features (`X`) and target (`y`).
- Perform a train/test split and explain why evaluating on unseen data is essential.

---

## 🧠 Key Concepts Covered

| Concept | Description |
|---|---|
| Supervised Learning | Training a model on labeled examples so it can predict outcomes on new, unseen data |
| Regression vs. Classification | Regression predicts a continuous number; classification predicts a category |
| Features (X) & Target (y) | X = the input columns the model learns from; y = the column being predicted |
| Scikit-learn API | A consistent 4-step workflow: **Instantiate → Fit → Predict → Score** |
| Train/Test Split | Splitting data so the model is evaluated on data it has never seen during training |

---

## 🧪 Hands-On Lab Summary

The notebook `day1_workflow.ipynb` walks through the following pipeline:

1. **Load Dataset** — Data is loaded and converted into a pandas DataFrame.
2. **Feature/Target Split** — The DataFrame is separated into `X` (features) and `y` (target).
3. **Train/Test Split** — An 80/20 split is performed using `train_test_split` with `random_state=42` for reproducibility.
4. **Shape Verification** — The shapes of `X_train`, `X_test`, `y_train`, and `y_test` are printed and validated with assertions to confirm consistency.
5. **Conceptual Reflection** — A Markdown cell explains, in the author's own words, why the model must never be evaluated on data it was trained on.

---

## ✅ Key Takeaway

> A model must never be evaluated on the same data it was trained on. Evaluating on a held-out test set is the only honest way to estimate how the model will perform on real, unseen data in production.

---

## 🛠️ Tools Used

- Python 3.10+
- Scikit-learn (`train_test_split`)
- Pandas
- Jupyter Notebook

---

## ▶️ How to Run

```bash
jupyter notebook day1_workflow.ipynb