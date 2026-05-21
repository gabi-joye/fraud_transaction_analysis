# Credit Card Fraud Detection with Random Forest
# Overview

This project explores how machine learning can be used to detect fraudulent banking transactions. Using a synthetic dataset from Kaggle, the project focuses on data cleaning, exploratory data analysis, feature relationships, and fraud prediction using a Random Forest classifier.

The dataset was intentionally designed with missing values and an imbalanced target variable to simulate real-world fraud detection challenges.

# Project Goals
Practice data cleaning and preprocessing techniques
Explore relationships between transaction variables
Handle missing data using multiple imputation methods
Analyze class imbalance in fraud datasets
Build and evaluate a Random Forest classification model
Interpret model performance using appropriate evaluation metrics
Dataset Information

The dataset contains 7,000 rows and includes the following features:

transaction_amount
hour_of_day
weekend_indicator
number_of_items
customer_age
previous_transactions
distance_from_home
device_type
network_quality
first_transaction
store_type
velocity_score
is_fraud (target variable)

The data was obtained from Kaggle and created for educational purposes.

# Data Cleaning & Preprocessing
Missing Value Handling

The dataset contained approximately 5,600 missing values across 12 columns. Instead of removing rows, several imputation methods were used to preserve the dataset size.

Imputation Methods Used
Variable Type	Method
Continuous numerical variables	Median imputation
Categorical/discrete variables	Mode imputation
Binary variables	Filled with 0
customer_age	Grouped median by store_type
distance_from_home	Grouped median by device_type and store_type
velocity_score	KNN imputation (k=5)
Exploratory Data Analysis (EDA)

# The following analyses and visualizations were performed:

Descriptive statistics using pandas.describe()
Count plots for fraud vs non-fraud transactions
Histograms of feature distributions
Pairplots (scatter matrices) using Seaborn
Correlation analysis using .corr()
Key Findings
The dataset is highly imbalanced.
Most variables showed weak linear correlations with the target variable.
distance_from_home was heavily right-skewed.
Fraud prediction likely depends on interactions between multiple variables rather than single-feature relationships.
Machine Learning Model
Model Used

A Random Forest Classifier was selected because it:

Handles nonlinear relationships effectively
Works well with mixed feature types
Is robust to noise and overfitting
Train-Test Split
75% training data
25% testing data
Model Evaluation
Accuracy

The model achieved approximately 88% accuracy.

However, due to class imbalance, accuracy alone was misleading because the model predicted nearly all transactions as non-fraudulent.

Confusion Matrix Findings

The confusion matrix revealed:

The model predicted almost all transactions as negative
Fraudulent transactions were not effectively identified
Recall for fraud detection was very poor
Important Evaluation Metrics

For fraud detection, the following metrics are more informative than accuracy:

Precision
Recall
F1-score
ROC-AUC
Future Improvements

# Potential improvements to the model include:

Undersampling the majority class
Hyperparameter tuning
Class weighting
Feature engineering
Testing alternative models such as XGBoost or LightGBM

# Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Learning Outcomes

# This project provided experience with:

Real-world data preprocessing
Missing value imputation strategies
Exploratory data analysis
Handling imbalanced datasets
Machine learning model evaluation
Fraud detection workflows
Machine learning model evaluation
Fraud detection workflows
