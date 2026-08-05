# Trees, Forests, SVMs & k-NN

### Week 3 - Day 4

## Overview:

On Day 4, I trained and compared four popular machine learning classification algorithms using Scikit-learn. The objective was to evaluate each model on the same dataset and determine which one achieved the best classification performance.

## Objectives:

- Train multiple classification models.
- Evaluate each model using common classification metrics.
- Compare model performance fairly.
- Select the best-performing model based on the F1-Score.

## Models Used:

- Decision Tree
- Random Forest
- Support Vector Machine (SVM)
- k-Nearest Neighbors (k-NN)

## Evaluation Metrics:

Each model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score

**The comparison was performed using the same train/test split to ensure a fair evaluation.**

## Results:

| Rank | Model | F1-Score | Accuracy |
|------|--------|----------|----------|
| A. | Decision Tree | 0.9666 | 0.9667 |
| B. | SVM | 0.9666 | 0.9667 |
| C. | k-NN | 0.9327 | 0.9333 |
| D. | Random Forest | 0.8997 | 0.9000 |

## Best Model:

The **Decision Tree** achieved the highest F1-Score and was selected as the best-performing model.

Although the **SVM** achieved identical evaluation metrics, the Decision Tree was ranked first after sorting the comparison table.

## What I Learned:

- How Decision Trees make rule-based predictions.
- How Random Forest combines multiple trees to improve robustness.
- How SVM separates classes using the maximum margin.
- How k-NN classifies samples based on neighboring data points.
- Why comparing multiple models on the same dataset is an essential step in machine learning.
- Why the F1-Score is often a better metric than Accuracy for evaluating classification models.

## Key Takeaway:

There is **no universally best machine learning algorithm**. The most reliable approach is to train multiple models, evaluate them using the same metrics, and choose the model that performs best for the specific dataset.