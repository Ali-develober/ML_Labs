# Data Preparation
The following steps were performed:

1-Loaded the dataset using Pandas

2-Converted trans_date_trans_time to datetime format

3-Checked for missing values

Selected numerical features such as:

amt

merch_long

# Scaling Techniques
Before applying PCA, feature scaling was applied:

Min-Max Scaling (values between 0 and 1)

Standardization (Z-score scaling)

Scaling ensures that all features contribute equally to PCA.

# Principal Component Analysis (PCA)
PCA was used to:

Reduce dimensionality

Transform features into principal components

Analyze explained variance ratio

This helps understand how much information is retained after transformation.

# File Format
Notebook: lab4.ipynb

Dataset: fraudTest.csv

File type: CSV

# Summary
This lab demonstrates the importance of data preprocessing and scaling before applying PCA. It provides practical experience in preparing transaction data for machine learning workflows.