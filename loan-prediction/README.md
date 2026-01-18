Predicting Loan Payback — Kaggle Playground Series

Overview

This project tackles a Kaggle Playground Series classification problem where the goal is to predict the probability that a borrower will pay back a loan. The evaluation metric is ROC AUC, emphasizing probability ranking over classification accuracy.

Dataset

Large tabular dataset with numerical and categorical features
No missing values
Moderately imbalanced target (~80% positive class)

Approach

Exploratory Data Analysis
Target distribution and feature inspection
Identification of skewed numerical features

Baseline Model

Logistic Regression with stratified train/validation split
Class-weight balancing for imbalanced target

Feature Engineering

Decomposed credit grade_subgrade
Loan affordability and risk interaction features
Domain-informed feature creation

Modeling

LightGBM classifier
Cross-validated hyperparameter tuning
Probability-based predictions optimized for ROC AUC

Results

Achieved ~0.92 ROC AUC on the Kaggle leaderboard
Strong agreement between public and private scores

Key Learnings

Tree-based models excel at tabular problems
ROC AUC is a better metric than accuracy for imbalanced datasets
Feature engineering + validation strategy matters more than excessive tuning

Files

Loan-payback.ipynb — complete notebook with EDA, modeling, and evaluation

Dataset is not included as it is a kaggle dataset which is available in kaggle.
