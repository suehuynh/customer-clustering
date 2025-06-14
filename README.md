# Customer Clustering for Bank Marketing

## Overview

This is a personal data science project inspired by the paper ["A data-driven approach to predict the success of bank telemarketing"](https://www.sciencedirect.com/science/article/abs/pii/S016792361400061X?via%3Dihub). 
> The goal was to explore whether adding unsupervised customer segmentation (via clustering) could improve marketing success prediction, especially in terms of model performance.

## Dataset

Source: [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing)

- 45,211 rows and 17 features describing client and campaign-related information

- Target variable: y (whether the client subscribed to a term deposit)

## Approach

### Feature Engineering

**Class Imbalance:** Handled using SMOTE

**Missing Values:** Filled using SimpleImputer

**Numerical Features:**
- Log transformation, Normalization, and Binning

**Categorical Features:**
- Binary encoding, Ordinal encoding, and Target encoding for job, poutcomes

### Clustering
- Create a cluster feature through PCA and K-Means

## Model Evaluation

Trained and evaluated three models on two datasets (with and without cluster feature):

- Logistic Regression
- XGBoost (XGBClassifier)
- LightGBM (LGBMClassifier)

Used K-Fold Cross Validation for performance estimation


## Results

- Cluster features slightly improved XGBoost and LightGBM performance.

- Logistic Regression did not benefit and even slightly declined.

## Implications

- Clustering can improve non-linear model performance by capturing latent customer group behaviors.
- Gains are minimal for linear models like logistic regression.
- Combining unsupervised clustering with supervised learning is a promising approach in marketing and customer segmentation.

## Tools & Libraries
- Python: pandas, numpy, scikit-learn, imbalanced-learn

- Models: XGBoost, LightGBM, Logistic Regression
- Visualization: matplotlib, seaborn

## Next Steps
- Try other clustering algorithms (e.g., DBSCAN, GMM)
- Extend analysis to new or real-world datasets


