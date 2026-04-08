## Logistic Regression and Classification

In this lab, I worked on an advertising dataset (advertising.csv) to practice classification modeling using Logistic Regression. The main goal was to build a model that predicts whether a user will click on an advertisement based on different features.

## Dataset

The dataset represents user behavior and contains information such as:

Daily time spent on the website
Age
Area income
Daily internet usage
Gender

The target variable used in this lab is Clicked on Ad, which indicates whether the user clicked on the advertisement (1) or not (0).

## Data Exploration

I started by loading the dataset using Pandas and performing basic exploration. I checked the dataset structure, data types, and summary statistics, and verified that there were no missing values or duplicate records.

To better understand the data, I created several visualizations:

Histogram of Age distribution
Jointplots to explore relationships between features
Pairplot to observe patterns between variables and the target

These visualizations helped identify patterns between user behavior and the likelihood of clicking on an ad.

## Data Cleaning

I checked for missing values and duplicate rows to ensure data quality. The dataset was clean, so no additional preprocessing was required.

## Feature Selection

I selected the most relevant numerical features for the model:

Daily Time Spent on Site
Age
Area Income
Daily Internet Usage
Male

I excluded non-numeric features such as country and timestamp since they are not directly useful for Logistic Regression.

## Machine Learning Model

I built a Logistic Regression model, which is used for classification problems. The model predicts the probability of a user clicking on an ad and classifies the result into either 0 or 1.

The dataset was split into:

Training set (70%)
Testing set (30%)

The model was trained using the training data and then used to make predictions on unseen test data.

## Model Evaluation

The model performance was evaluated using a classification report, which includes:

Precision
Recall
F1-score
Accuracy

These metrics helped measure how well the model distinguishes between users who clicked on the ad and those who did not.