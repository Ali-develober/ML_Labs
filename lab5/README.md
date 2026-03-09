# ARTI308 – Lab 5  
## Feature Engineering and Model Evaluation

In this lab, I worked on a food delivery dataset (`talabat_enhanced_orders.csv`) to practice feature engineering, preprocessing, and machine learning model evaluation. The main goal was to improve the predictive performance of a model by creating meaningful features and testing different configurations.

## Dataset

The dataset represents food delivery orders and contains information about order details, restaurant and customer locations, delivery distance, traffic level, item names, quantities, total order price, and delivery outcomes.

The target variable used in this lab is **Order_Status**, which represents the final status of the order.

## Data Exploration

I first loaded the dataset using **Pandas** and performed basic exploration. I checked the dataset shape, inspected the data types, identified missing values, checked for duplicate rows, and visualized the distribution of the target variable. This helped me understand the structure of the dataset before applying any transformations.

## Feature Engineering

To improve the model performance, I created several engineered features.

### Time-Based Features
From the `Order_Time` column I extracted:
- `order_hour`
- `order_dayofweek`
- `is_weekend`
- `is_peak_hour`

These features help the model capture ordering patterns during busy hours or weekends.

### Price-Based Feature

I created a new feature called **price_per_item**, which was calculated as:

price_per_item = Total_Price / Quantity

This feature helps represent the relative price of each ordered item.

### Geographic Feature

Using the restaurant and customer coordinates, I calculated the **Haversine distance** between them and stored it in the feature:

haversine_rest_to_cust_km

This represents the real geographic distance between the restaurant and the customer.

### Item Category Reduction

The `Item_Name` column contained many unique values. To reduce dimensionality, I kept only the most frequent items and grouped the remaining ones under the category **Other**. The resulting feature was called:

Item_Name_reduced

### Price Tier Feature

I categorized total order prices into different levels:
- low
- medium
- high
- very_high

This feature was stored in **price_tier** to help the model understand price ranges more easily.

## Machine Learning Model

I built a **Random Forest Classifier** using a pipeline that includes preprocessing and modeling. I used a **ColumnTransformer** to apply OneHotEncoding for categorical variables and pass numerical features directly to the model. This allowed the model to handle mixed data types efficiently.

## Model Evaluation

The model performance was evaluated using:
- Accuracy score
- Classification report
- Confusion matrix

I also analyzed **feature importance** to understand which variables had the most impact on the prediction.

## Feature Selection

I applied **feature selection using Random Forest importance with SelectFromModel** to remove less important features. I compared the performance of the baseline model with the model after feature selection to determine whether removing features improves performance.

## Student Tasks

### Task 1 – Create a New Feature

I created a new engineered feature called **traffic_distance_pressure**. This feature combines delivery distance with traffic level to represent delivery difficulty.

traffic_distance_pressure = Delivery_Distance_km × Traffic_Level

This helps capture situations where long delivery distances combined with high traffic may increase the likelihood of delivery delays.

### Task 2 – Compare Peak Hour Rules

I experimented with a different rule for defining peak hours and compared it with the baseline rule. This allowed me to observe whether redefining busy hours improves the model performance.

### Task 3 – Test Different Top-K Item Groups

I tested different values for reducing item categories:
- Top 10 items
- Top 30 items
- Top 50 items

I compared the model accuracy and observed how the number of item categories affects the model.

### Task 4 – Compare Baseline vs Feature Selection

Finally, I compared the performance of the baseline model with the model after feature selection to evaluate whether removing less important features improves prediction performance.

## Conclusion

In this lab, I applied feature engineering techniques to a real-world dataset. By creating meaningful features, reducing high-cardinality variables, and experimenting with different configurations, I was able to analyze how feature design affects machine learning model performance. The lab demonstrated the importance of feature engineering in improving model interpretability and predictive capability.