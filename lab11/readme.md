## ARTI308 – Lab 11
## Credit Card Customer Segmentation using K-Means Clustering

In this assignment, I worked on a real-world credit card dataset to apply unsupervised learning using K-Means clustering. The main objective was to group credit card customers into meaningful segments based on their usage behavior, without any predefined labels.

## Dataset

The dataset contains **8,950 credit card holders** with **18 behavioral features** describing how each customer uses their card.

Key features include:

- BALANCE – the amount left on the account
- PURCHASES – total amount of purchases made
- ONEOFF_PURCHASES – largest single purchase amount
- INSTALLMENTS_PURCHASES – amount of purchases done in installments
- CASH_ADVANCE – amount of cash taken in advance
- CREDIT_LIMIT – credit limit for the customer
- PAYMENTS – total amount paid by the customer
- MINIMUM_PAYMENTS – minimum amount paid
- TENURE – number of months the customer has been active

There is no target variable. The goal is to **discover hidden groups** within the data.

## Data Cleaning

Before modeling, I cleaned the dataset by:

- Dropping the `CUST_ID` column, since it is just a unique identifier and carries no behavioral information
- Checking for missing values — `CREDIT_LIMIT` had **1 missing value** and `MINIMUM_PAYMENTS` had **313 missing values**
- Filling all missing values using **mean imputation** to preserve the overall data distribution without removing rows

## Exploratory Data Analysis

I explored the data visually before applying clustering:

- **Histograms** for all features revealed that most distributions are right-skewed, meaning most customers have low-to-moderate usage with a few extreme outliers
- **Correlation heatmap** showed strong relationships between PURCHASES, ONEOFF_PURCHASES, and PURCHASES_TRX, which makes sense as they all relate to buying activity
- **Scatter plot of BALANCE vs PURCHASES** showed that most customers either carry a high balance or make many purchases, but rarely both
- **Scatter plot of BALANCE vs CASH_ADVANCE** revealed a distinct group of customers who carry high balances and rely heavily on cash advance

## Feature Scaling

Since K-Means is a **distance-based algorithm**, all features must be on the same scale before clustering.

Features like `BALANCE` and `CREDIT_LIMIT` have values in the thousands, while frequency features like `PURCHASES_FREQUENCY` range between 0 and 1. Without scaling, the large-magnitude features would dominate the distance calculations.

I used **StandardScaler** to scale all features to have a mean of 0 and a standard deviation of 1 before fitting the model.

## Choosing the Optimal K

### Elbow Method

I ran K-Means for K values from 1 to 10 and plotted the inertia (within-cluster sum of squares) for each. The curve showed a noticeable bend around **K=3**, after which the reduction in inertia became much smaller.

### Silhouette Score

I also computed the silhouette score for K values from 2 to 10. The results were:

| K | Silhouette Score |
|---|-----------------|
| 2 | 0.2100 |
| 3 | 0.2506 |
| 4 | 0.1976 |
| 5 | 0.1932 |
| 6 | 0.2026 |
| 7 | 0.2150 |
| 8 | 0.2081 |
| 9 | 0.2149 |
| 10 | 0.2205 |

K=3 produced the highest silhouette score, confirming it as the best choice. It also aligns with the elbow curve and results in three interpretable customer segments.

## Final K-Means Model

The final model was trained with K=3, random_state=42, and n_init=10 to ensure stable results. The cluster labels were added back to the original dataframe in a new column called Cluster.

## Cluster Analysis

After grouping by cluster and computing the mean of each feature, three distinct customer profiles emerged:

- **Cluster 0 – Inactive / Low-activity customers**: Low balance, very few purchases, low credit limit, and minimal card usage. These customers appear to be dormant or infrequent users who barely engage with their credit card.

- **Cluster 1 – High-spender / Active customers**: High purchases, high credit limit, high payments, and frequent transaction activity. These are the most engaged customers and likely represent the highest-value segment for the company.

- **Cluster 2 – Cash advance users**: High cash advance amounts, high cash advance frequency, but low purchases. These customers use the credit card primarily as a source of cash rather than for shopping, which may indicate financial stress.

## Visualization with PCA

Since the dataset has 17 features after dropping CUST_ID, it is not possible to visualize the clusters directly. I used PCA (Principal Component Analysis) to reduce the data to 2 dimensions for visualization only.

The PCA scatter plot showed three broadly separated regions corresponding to the three clusters. Some overlap was expected because PCA compresses 17 dimensions into just 2, and not all variation can be captured in a 2D view.

## Observations

- The dataset has significant skewness and outliers in many features, which is common in financial data
- K=3 gave the best silhouette score and also produced the most interpretable business segments
- The cash advance cluster was the most distinct and easy to identify from the scatter plots, even before clustering
- High-value customers in Cluster 1 had notably higher credit limits and total payments compared to the other groups

## Conclusion

This assignment demonstrated how to apply K-Means clustering to a real financial dataset for customer segmentation. The pipeline included data cleaning, exploratory analysis, feature scaling, selecting the optimal number of clusters using both the elbow method and silhouette score, and interpreting the resulting segments.

The three clusters revealed meaningful differences in customer behavior, which a company could use to design targeted marketing strategies — such as re-engagement campaigns for inactive customers, loyalty rewards for high-spenders, and financial products for cash advance users.

K-Means proved to be a practical and effective approach for this type of unsupervised segmentation task.