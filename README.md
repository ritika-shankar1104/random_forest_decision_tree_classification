# Random Forest & Decision Tree Classification

**Language:** R &nbsp;|&nbsp; **Domain:** Machine Learning · Clinical Diagnosis  
**Skills:** Decision Trees · Random Forest · Model Evaluation · caret Pipeline

---

## Overview

A supervised machine learning pipeline for clinical classification — comparing a single decision tree with an ensemble random forest model on a pre-split clinical diagnosis dataset. Demonstrates the standard ML workflow from data ingestion through to test-set performance evaluation.

**Dataset:** Custom clinical dataset with a pre-defined train/test split (`set` column) — binary `diagnosis` outcome with biological predictors.

---

## Pipeline

### 1. Data Ingestion & Preprocessing
- Loaded from Excel using `readxl`
- Split into training (427 observations) and test (142 observations) using the provided `set` column
- Removed non-predictive identifiers (`id`, `set`) before modelling

### 2. Decision Tree
- Fitted using `rpart` with default parameters
- Visualised with `rpart.plot` to show the splitting rules at each node
- Pruned to reduce overfitting using the complexity parameter (cp)

### 3. Random Forest
- Fitted using `randomForest` — ensemble of 500 decision trees
- Tuned `mtry` (number of features per split) with `caret::train()`
- Variable importance plot to identify the most influential predictors

### 4. Model Evaluation
- Confusion matrix, accuracy, sensitivity, and specificity on the held-out test set
- Comparison of single tree vs. ensemble performance — random forest consistently outperforms the single tree

---

## Key Packages

`rpart` · `rpart.plot` · `randomForest` · `caret` · `readxl`

---

## Skills Demonstrated

- Full supervised ML pipeline from raw data to test-set evaluation
- Decision tree interpretation and pruning strategy
- Random forest ensemble learning with hyperparameter tuning
- `caret` framework for standardised model training and cross-validation
