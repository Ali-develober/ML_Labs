# Fraud Detection Dataset

## About the Dataset

This dataset contains credit card transaction records that are used for fraud detection. 
Each row represents a single transaction made by a customer, and the goal is to determine whether that transaction is legitimate or fraudulent.

The dataset combines transactional data, customer details, merchant information, and geographical attributes in one structured CSV file.

---

## Data Composition

Each transaction record includes:

### Transaction Features
- `trans_date_trans_time`: The exact date and time of the transaction  
- `amt`: Transaction amount  
- `is_fraud`: Target variable indicating whether the transaction is fraudulent (1) or legitimate (0)  

### Customer Information
- Customer name (first, last)
- Gender
- Date of birth
- Job
- Residential address (street, city, state, zip)
- Customer geographic coordinates (lat, long)
- City population (`city_pop`)

### Merchant Information
- Merchant name
- Merchant category
- Merchant geographic coordinates (`merch_lat`, `merch_long`)

---

## Machine Learning Perspective

This dataset is structured as a **binary classification problem**, where the target variable is is_fraud.

- 0 → Legitimate transaction  
- 1 → Fraudulent transaction  

One important characteristic of this dataset is that it is **highly imbalanced**. Fraudulent transactions represent only a very small percentage of the total data. This imbalance makes the problem more challenging and realistic, since fraud detection systems in real-world applications must handle rare but critical events.

Because of this imbalance, standard accuracy metrics alone may not be sufficient. The dataset is more suitable for evaluating models using metrics such as:
- Precision
- Recall
- F1-score

This makes the dataset particularly useful for studying:
- Imbalanced classification techniques
- Fraud detection models
- Anomaly detection approaches
- Feature engineering and preprocessing strategies


## File Format

- File type: CSV  
- Each row represents a single transaction  
- No pre-aggregation applied  
- Contains both numerical and categorical features  


## Summary

Overall, this dataset provides a realistic representation of financial transaction data and is suitable for building and evaluating fraud detection models under imbalanced conditions.
