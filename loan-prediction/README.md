# 📊 Predicting Loan Payback — Kaggle Playground Series

## Project Overview
This repository presents an end-to-end machine learning solution for predicting the **probability that a borrower will pay back a loan**, developed as part of a Kaggle Playground Series competition.

The project emphasizes **clean tabular modeling practices**, **robust validation**, and **probability-based evaluation using ROC AUC**, closely reflecting real-world credit risk modeling workflows.

The final model achieves a **ROC AUC of ~0.92** on the Kaggle leaderboard, with strong alignment between public and private scores.

---

## Problem Statement
Given borrower demographics, financial attributes, and loan characteristics, predict the probability that a loan will be paid back.

- **Task**: Binary classification  
- **Target variable**: `loan_paid_back`  
- **Evaluation metric**: Area Under the ROC Curve (ROC AUC)  
- **Output**: Predicted probabilities (not class labels)

ROC AUC is used due to moderate class imbalance and its focus on ranking quality rather than fixed decision thresholds.

---

## Dataset Characteristics
- Large-scale tabular dataset (~600k rows)
- Combination of numerical and categorical features
- No missing values
- Moderately imbalanced target (~80% positive class)

The dataset structure closely resembles real-world credit risk data, making it suitable for applied machine learning techniques.

---

## Methodology

### 1. Exploratory Data Analysis
- Inspected feature distributions and summary statistics
- Identified right-skewed numerical variables (e.g., income, loan amount)
- Analyzed class distribution to inform metric and validation strategy

---

### 2. Baseline Model
- **Logistic Regression**
  - Stratified train/validation split
  - Probability-based predictions
  - ROC AUC used for evaluation
- Served as a sanity check and performance baseline

---

### 3. Feature Engineering
Feature engineering was guided by **domain intuition** and **interpretability**, focusing on high-signal transformations:

- **Credit grade decomposition**
  - Split `grade_subgrade` into `grade` and `subgrade`
- **Affordability ratios**
  - Loan amount relative to annual income
- **Risk interaction features**
  - Combined interest rate and debt-to-income ratio

These features explicitly capture borrower affordability and compounding risk effects.

---

### 4. Model Selection
- **LightGBM (Gradient Boosted Decision Trees)**
  - Strong performance on structured tabular data
  - Captures non-linear relationships and feature interactions
  - No scaling required for numerical features

Categorical variables were handled using LightGBM’s native categorical feature support.

---

### 5. Validation & Tuning
- **Stratified K-Fold Cross-Validation**
  - Preserved class distribution across folds
  - Produced stable and reliable ROC AUC estimates
- **RandomizedSearchCV**
  - Tuned high-impact hyperparameters
  - Balanced performance gains with computational efficiency

---

### 6. Final Training & Submission
- Trained the best-performing model on the full training dataset
- Generated probability predictions for the test set
- Created submission files following Kaggle’s required format

---

## Results
- **ROC AUC ≈ 0.92**
- Minimal gap between public and private leaderboard scores
- Indicates strong generalization and a reliable validation strategy

---

## Key Learnings
- Gradient boosting models excel on tabular datasets
- Proper validation strategy is critical for trustworthy performance
- Domain-informed feature engineering often outperforms excessive tuning
- ROC AUC is the appropriate metric for imbalanced, probability-based tasks

---

## Repository Contents
- `Loan-payback.ipynb` — End-to-end notebook including:
  - Data loading and EDA
  - Feature engineering
  - Model training and evaluation
  - Submission generation

---

## Tools & Libraries
- Python
- pandas, NumPy
- scikit-learn
- LightGBM
- Matplotlib

---

## Data Availability
The dataset used in this project is provided by Kaggle as part of the Playground Series competition.  
Due to Kaggle’s data usage terms, the dataset is **not included** in this repository.

The notebook is designed to run with data downloaded directly from Kaggle.

---

## Notes
This project was developed as a learning and portfolio exercise, with an emphasis on **clean modeling practices**, **interpretability**, and **robust evaluation**, rather than leaderboard optimization alone.
