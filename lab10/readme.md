## ARTI308 – Lab 10
## Classification Modeling using Support Vector Machines

In this assignment, I worked on the famous Iris flower dataset to apply classification techniques using Support Vector Machines (SVM). The main objective was to predict the species of an iris flower based on its physical measurements.

## Dataset

The dataset includes 150 samples from three species of Iris flowers:

- Iris Setosa (n=50)
- Iris Versicolor (n=50)
- Iris Virginica (n=50)

The four features of the Iris dataset:

- Sepal length in cm
- Sepal width in cm
- Petal length in cm
- Petal width in cm

The target variable is **species**, which indicates the type of iris flower.

## Data Exploration

I loaded the dataset using Seaborn's built-in `load_dataset()` function and explored it using Pandas by checking its structure and summary statistics.

To understand the data better, I visualized the relationships between features using:

- Pairplot to observe how features relate to each other across all three species
- KDE plot to analyze the distribution of sepal length versus sepal width for the Setosa species

These visualizations revealed that **Setosa** is the most separable species, as it forms a clearly distinct cluster from the other two species.

## Feature Selection

All four measurements were used as input variables (X), while the target variable **species** was used as the output (y).

The data was split into training and testing sets using a 70/30 ratio.

## Machine Learning Model

### Support Vector Machine (SVM)

A Support Vector Classifier (SVC) was trained on the dataset using Scikit-Learn's `SVC()` with default parameters.

## Model Evaluation

The model was evaluated using:

- Confusion Matrix
- Classification Report (Precision, Recall, F1-score)

The initial model produced strong results, correctly classifying most samples across all three species.

## Gridsearch Hyperparameter Tuning

To further optimize the model, I used `GridSearchCV` to search for the best combination of hyperparameters.

A parameter grid was defined with different values for **C** and **gamma**, and the grid search was run with 5-fold cross-validation.

The best parameters were then used to generate new predictions, which were evaluated using a confusion matrix and classification report.

## Observations

The SVM model performed very well on the Iris dataset even before tuning, due to the relatively clean and separable nature of the data. The Setosa species was predicted with perfect accuracy, while minor misclassifications occurred between Versicolor and Virginica.

GridSearch confirmed that the default or near-default parameters were already close to optimal for this dataset.

## Conclusion

This assignment demonstrated how to apply Support Vector Machines for multi-class classification. It also highlighted the usefulness of GridSearchCV for hyperparameter tuning, even when the baseline model is already performing well.

SVM proved to be an effective classifier for the Iris dataset, especially given the clear separability of the Setosa class.