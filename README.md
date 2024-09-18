# Tree-Based Methods and SMOTE on APS Failure Data

## Project Overview

This project focuses on **Tree-Based Methods** and using **SMOTE (Synthetic Minority Over-sampling Technique)** to handle class imbalance in the **APS Failure dataset**. The dataset contains data from Scania trucks, where the goal is to classify failures in the Air Pressure System (APS) components. This homework involves data preparation, training various tree-based models, applying class imbalance correction techniques, and analyzing the performance.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Task 1: Tree-Based Methods](#task-1-tree-based-methods)
- [Task 2: SMOTE for Class Imbalance](#task-2-smote-for-class-imbalance)
- [How to Run](#how-to-run)
- [Results](#results)
- [License](#license)

## Dataset

### APS Failure Dataset
- **Source**: [UCI Machine Learning Repository - APS Failure at Scania Trucks](https://archive.ics.uci.edu/ml/datasets/APS+Failure+at+Scania+Trucks)
- **Data Description**:
  - The dataset consists of operational data from Scania trucks.
  - The positive class represents failures in the APS, while the negative class represents failures unrelated to the APS.
  - The dataset has missing values and a severe class imbalance, with 1,000 positive examples and 59,000 negative examples in the training set.

## Task 1: Tree-Based Methods

### (a) Data Preparation
- The dataset contains missing values. A data imputation technique was applied to handle these missing values. Additionally, the **Coefficient of Variation (CV)** was calculated for each feature to determine the most variable features for visualization.

### (b) Feature Visualization
- A **correlation matrix** was plotted to explore the relationships between features. The top features with the highest CV were visualized using scatter plots and box plots to investigate their significance.

### (c) Random Forest Classifier
- A **Random Forest** classifier was trained on the APS Failure dataset **without compensating for class imbalance**. The following metrics were reported:
  - Confusion Matrix
  - ROC Curve
  - AUC
  - Misclassification Rate
  - Out-of-Bag (OOB) error estimate was calculated and compared with the test error.

### (d) Addressing Class Imbalance in Random Forest
- To address the class imbalance, the random forest was trained with compensation for class imbalance. The model was evaluated again, and the results were compared with those from the uncompensated model.

### (e) XGBoost and Model Trees
- **XGBoost** was used to fit a **model tree** with **L1-penalized logistic regression** at each node. The regularization term (α) was determined using cross-validation. The model was evaluated using:
  - 5-fold, 10-fold, and Leave-One-Out Cross Validation.
  - Confusion Matrix
  - ROC Curve
  - AUC

## Task 2: SMOTE for Class Imbalance

### (a) Applying SMOTE
- **SMOTE** was applied to the training data to handle class imbalance. This technique generates synthetic data points to balance the positive and negative classes.

### (b) XGBoost with SMOTE
- The **XGBoost** model was trained again using the **SMOTE**-processed data. The same evaluation metrics as in Task 1 were used, and the results were compared with the models trained without SMOTE.

## How to Run

### Requirements

- Python 3.x
- Jupyter Notebook
- Required Python libraries (can be installed via `pip`):
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `scikit-learn`
  - `xgboost`
  - `imbalanced-learn`

### Instructions

1. Clone the repository and navigate to the project folder.
2. Open the Jupyter Notebook (`Huang_Bor-Sheng.ipynb`).
3. Run the notebook cells to execute the tasks and view the results.

## Results

- **Random Forest**: The model was evaluated with and without compensation for class imbalance. The confusion matrix, ROC, AUC, and misclassification rate were reported for both cases.
- **XGBoost**: The performance of XGBoost was compared before and after applying SMOTE, highlighting the effect of handling class imbalance using synthetic over-sampling.

## License

This project is intended for academic purposes and is based on the DSCI 552 course material.

