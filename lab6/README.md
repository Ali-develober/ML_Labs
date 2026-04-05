## ARTI308 – Lab 6
## Regression Modeling and Model Evaluation

In this lab, I worked on a housing dataset (USA_Housing.csv) to practice regression modeling, data exploration, and machine learning evaluation. The main goal was to build a predictive model that estimates house prices based on different numerical features.

## Dataset

The dataset represents housing data and contains information about average area income, house age, number of rooms and bedrooms, area population, and house prices.

The target variable used in this lab is Price, which represents the house price to be predicted.

## Data Exploration

I first loaded the dataset using Pandas and performed basic exploration. I checked the dataset shape, inspected data types, reviewed summary statistics, and verified whether there were missing values or duplicate records.

To better understand the data, I visualized feature relationships and distributions using pairplots, histograms, and a correlation heatmap. This helped identify how different features are related to the target variable (Price).

## Data Cleaning

I checked for missing values and duplicate rows to ensure data quality. The dataset was already clean, so no additional preprocessing or data cleaning steps were required.

## Feature Selection

I selected the relevant numerical features for building the model:

Avg. Area Income
Avg. Area House Age
Avg. Area Number of Rooms
Avg. Area Number of Bedrooms
Area Population

I excluded the Address column because it is a text-based feature and not suitable for Linear Regression.

## Machine Learning Model

I built a Linear Regression model to predict house prices. The dataset was split into training and testing sets (60% training, 40% testing). The model was trained using the training data and then evaluated on unseen test data.

## Model Evaluation

The model performance was evaluated using:

Mean Absolute Error (MAE)
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)

## I also visualized the results using:

A scatter plot of actual vs predicted values
A histogram of residual errors

These evaluation methods helped assess how well the model performs and how close the predictions are to the actual values.