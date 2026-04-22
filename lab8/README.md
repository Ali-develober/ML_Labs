## ARTI308 – Lab 8
## Classification Modeling and Model Optimization  

In this assignment, I worked on a classification dataset (KNN_Project_Data) to practice K-Nearest Neighbors (KNN), data preprocessing, and model evaluation. The main goal was to build a classification model that predicts the target class based on multiple numerical features.

## Dataset  

The dataset contains several anonymized numerical features along with a target column called **TARGET CLASS**, which represents the class label to be predicted.

All feature names are hidden, but they are already prepared for machine learning tasks.

## Data Exploration  

I first loaded the dataset using Pandas and performed basic exploration. I checked the dataset structure, data types, and summary statistics to better understand the data.

To visualize relationships between features and the target variable, I used a **pairplot** with hue set to TARGET CLASS. This helped in observing how the classes are distributed across different features.

## Data Preprocessing  

Since KNN is a distance-based algorithm, feature scaling is very important. I applied **StandardScaler** to normalize the feature values so that all features contribute equally to the distance calculation.

The scaled features were then stored in a new DataFrame for further processing.

## Feature Selection  

All numerical features in the dataset were used as input variables (X), while **TARGET CLASS** was used as the output variable (y).

No columns were removed since all features are already suitable for modeling.

## Machine Learning Model  

I built a **K-Nearest Neighbors (KNN)** classification model.  

The dataset was split into training and testing sets using a 70% training and 30% testing ratio.

Initially, I trained the model with **K = 1** to evaluate the baseline performance.

## Model Evaluation  

The model performance was evaluated using:

- **Confusion Matrix**
- **Classification Report** (Precision, Recall, F1-score)

These metrics helped assess how well the model classified the data.

## Choosing the Optimal K Value  

To improve the model, I tested multiple values of K (from 1 to 39) and calculated the error rate for each value.

I then plotted **Error Rate vs K Value** to identify the optimal K that minimizes the error.

## Final Model  

After selecting the best K value based on the error rate plot, I retrained the KNN model using that value.

The final model showed improved performance compared to the initial model.

## Conclusion  

This assignment demonstrated how to apply KNN for classification problems, the importance of feature scaling, and how to optimize model performance by selecting the appropriate value of K.

It also highlighted the importance of evaluation metrics and visualization techniques in understanding model behavior.