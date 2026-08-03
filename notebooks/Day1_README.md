# Supervised Learning Concepts & the Scikit-learn API 

**Week 3 - Day 1**

## Learning Objectives:

In this notebook, we will cover:

1. Load a provided dataset (and I used california housing) and separate it into **features** X and **target** y.
2. Perform an 80/20 **train/test split** with a fixed random_state.
3. Confirm the shapes of **X_train, X_test, y_train, y_test** are consistent and print them.
4. In a Markdown cell, explain in your own words why the model must never see the test set during training.
   
> Note: Words written in bold represents key topics that were studied and covered during the day.


## Hands-On Lab Summary:

The notebook "Day1.ipynb" walks through the following pipeline:

1. **Load Dataset** — Data is loaded and converted into a pandas DataFrame.
2. **Feature/Target Split** — The DataFrame is separated into (X) -> features and (y) -> (target).
3. **Train/Test Split** — An 80/20 split is performed using "train_test_split" with random_state=42 for reproducibility.
4. **Shape Verification** — The shapes of (X_train, X_test, y_train, and y_test) are printed and validated with assertions to confirm consistency.
5. **Conceptual Reflection** — A Markdown cell explains (in my own words), why the model must never be evaluated on data it was trained on.


## Key Takeaway:

> A model must never be evaluated on the same data it was trained on. Evaluating on a held-out test set is the only honest way to estimate how the model will perform on real, unseen data in production.


## Tools Used:

- Python 
- Scikit-learn 
- Pandas
- Jupyter Notebook
