## ARTI308 – Lab 9
## Classification Modeling using Tree-Based Algorithms  

In this assignment, I worked on a loan dataset (loan_data.csv) to apply classification techniques using Decision Trees and Random Forest models. The main objective was to predict whether a loan would be fully paid or not based on financial and customer-related features.

## Dataset  

The dataset includes several features such as credit policy, interest rate, installment amount, annual income, debt-to-income ratio, FICO score, and loan purpose.

The target variable is **not.fully.paid**, which indicates whether the borrower failed to fully repay the loan.

## Data Exploration  

I explored the dataset using Pandas by checking its structure, data types, and summary statistics.

To understand the data better, I visualized the relationships between features using:

- Histograms of FICO score based on credit policy and loan repayment status  
- Countplot of loan purposes grouped by repayment status  
- Jointplot to analyze the relationship between FICO score and interest rate  
- Lmplot to compare trends across different categories  

These visualizations helped reveal patterns and differences between groups.

## Data Preprocessing  

Since the **purpose** column is categorical, I converted it into numerical form using dummy variables with `pd.get_dummies()`. This step is required for machine learning models.

The processed dataset was stored in a new dataframe called `final_data`.

## Feature Selection  

All features were used as input variables (X), while the target variable **not.fully.paid** was used as the output (y).

The data was split into training and testing sets using a 70/30 ratio.

## Machine Learning Models  

### Decision Tree  

A Decision Tree classifier was trained on the dataset to perform classification.

### Random Forest  

A Random Forest classifier was also trained to improve performance by combining multiple decision trees.

## Model Evaluation  

Both models were evaluated using:

- Confusion Matrix  
- Classification Report (Precision, Recall, F1-score)  

The evaluation showed that the Random Forest model performed better overall.

## Observations  

The classification report revealed that the model performed poorly on class 1 (loans not fully paid). The recall and F1-score for this class were very low, indicating difficulty in predicting the minority class.

This suggests that the dataset is imbalanced, and the model is biased toward predicting the majority class.

## Conclusion  

This assignment demonstrated how to use Decision Trees and Random Forest for classification problems. It also highlighted the importance of handling categorical data and evaluating model performance carefully.

Random Forest provided better results than Decision Tree, but both models struggled with class imbalance.