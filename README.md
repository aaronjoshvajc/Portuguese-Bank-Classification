# Portuguese Bank Marketing Campaign – Binary Classification
This project aims to build a binary classification model to predict whether a customer will subscribe to a term deposit, based on historical data from a Portuguese bank marketing campaign.

# Problem Statement
The dataset contains marketing data with three main types of features:

Customer Details (e.g., age, job, marital status)

Campaign Details (e.g., contact method, number of contacts)

Previous Marketing Interactions (e.g., outcome of previous calls)

The target variable y indicates whether the client subscribed to a term deposit (yes or no).

# Project Workflow
## Exploratory Data Analysis (EDA)
Verified there were no missing values

Conducted univariate and bivariate analysis on numerical and categorical variables

Found skewness in campaign and previous

Used correlation heatmap and target-wise plots for better insights

## Preprocessing & Feature Engineering
Created binary target variable y_binary

Engineered new features:

was_contacted_before – if client was previously contacted

had_success_before – if client previously subscribed

Age and Job grouping

Dropped features like duration and poutcome to prevent data leakage

Applied:

Binary encoding

One-hot encoding

Ordinal encoding

Scaled features with StandardScaler

## Train-Test Split
Used stratified sampling to maintain class balance (since data is imbalanced)

## Model Building
Several classification models were tested:

Logistic Regression – baseline model

Random Forest Classifier

XGBoost Classifier

Used SMOTE to address class imbalance

Hyperparameter tuning with RandomizedSearchCV

## Evaluation Metrics
Best Model: XGBoost with tuned hyperparameters

ROC AUC Score: 0.74

Recall (Class 1 - buyers): 61%

Precision (Class 0 - non-buyers): High

Significantly better than baseline models and SMOTE-RFC

## Model Saving
Final model was saved using joblib for deployment or future inference.

## Insights & Conclusions
Clients previously contacted and with successful history are more likely to subscribe

Age and job groupings influence decisions

Optimizing for recall on buyers helps reduce missed opportunities in marketing
