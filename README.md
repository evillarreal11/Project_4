# Project 4: Credit Card Fraud Detection - Machine Learning

![image](https://github.com/evillarreal11/Project_4/assets/89103450/56f6bd14-cdbd-4b56-9b12-8366c870e9d4)

**Dataset source:** https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud 

**This code utilizes Google Colab. Below are requirements before getting started:**

- The dataset will need to be downloaded from Kaggle.
- Spark version 3.4.2 will need to be installed.
- The files need to be moved into "My Drive" in Google Drive and a folder should be created called "Trained Models"
- Once prompted, you will need to allow access to your entire Google Drive for the code to run.

# Overview

The dataset contains transactions made by credit cards in September 2013 by European cardholders.

This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.

# Data Analysis

Through the initial deepdive of the dataset, we were able to discover a few things:

- The average Fraudulent Charge was $123.87
- The average True Charge was $88.41
- 0.606 seconds between every transaction
- 0.607 seconds between every true transaction
- 351 seconds between every fraudulent transaction


# Machine Learning - Logistic Regression Model

**Original data:**

*0: Normal* 

- High percentage of correct predictions
- High recall of positive cases
- High percentage of positive predictions that were correct

*1: Fraudulent*

- Somewhat low percentage of correct predictions.
- Low recall of positive cases
- Low percentage of positive predictions that were correct.

*Confusion matrix*

- Highly unbalanced dataset
- Shows that the Normal or 0 class yielded a “true positive” result with the predicted and actual data, the Fraudulent or 1 class did not.

**Rebalanced data:**

The model utilizes the Random Oversampler, whic is a random selection of examples from the minority class, with replacement, and adds them to the training dataset.

*0: Normal and 1: Fraudulent (overall)*

- High percentage of correct predictions
- High recall of positive cases
- High percentage of positive predictions that were correct.
- The Normal class slightly decreased in its prediction ability after being rebalanced.

*Confusion Matrix*

- Shows high True Positive and True Negative classes, which refers to the Normal and Fraudulent charges being classified correctly.
- Thus, our model was successful and able to make accurate predictions.

# Widgets
Using the sample code provided in class, we wanted to create an interactive way to test and experiment with the predictive capabilities of our model. The first widget shown in “Project4_Widgets” calls the model created with the rebalanced data, and the second uses a pared down model that only includes features with a correlation of greater than .15 in magnitude
- The user can slide the scale for each variable in the model, and the number in the square brackets will indicate a 0 or 1 for normal or fraudulent transactions. 
- While both widgets will predict the class of the transaction, the pared down model is more user friendly and allows someone to focus in on the variables that have the greatest impact in relation to credit card fraud.
- The features included, although anonymized through PCA, could be geographic information, transaction type, or merchant type, among other things. 
