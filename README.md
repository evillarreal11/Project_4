# Project 4: Credit Card Fraud Detection - Machine Learning

![image](https://github.com/evillarreal11/Project_4/assets/89103450/56f6bd14-cdbd-4b56-9b12-8366c870e9d4)

**This code utilizes Google Colab. Below are requirements before getting started:**

- The dataset will need to be downloaded from Kaggle.
- Spark version 3.4.2 will need to be installed.
- The files need to be moved into "My Drive" in Google Drive.
- Once prompted, you will need to allow access to your entire Google Drive for the code to run.

# Overview

**Dataset source:** https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud 

The dataset contains transactions made by credit cards in September 2013 by European cardholders.

This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.
