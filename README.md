# Predicting-and-Understanding-Customer-Attrition

## Project Title:
### Customer Churn Analysis in Banking: Insights & Predictive Modelling
### Project Description
This project analyzes pizza sales data using **SQL** to generate insights into revenue, customer behaviour, and sales trends. It aims to help businesses understand sales performance, customer preferences, and operational efficiency.
## Objectives:
- `Import & Validate Data:` Load and ensure the quality of two customer data tables.
- `Data Preprocessing:` Clean, merge, and prepare the data for analysis.
- `Exploratory Data Analysis (EDA):` Analyze churn patterns to uncover insights.
- `Model Development:` Build a predictive classification model to estimate churn probability.
- `Model Interpretation & Insights:` Interpret model results and translate them into actionable business insights.

### Data Preparation and Cleaning:
- Some libraries are used for data manipulation, numerical computations, and visualization.
- Data from two sheets are read — one for customer demographics and another for account-level details.
- Datasets are merged on the CustomerId column to create a unified dataset.

## Data Cleaning Steps:

- Removed duplicates and irrelevant columns.
- Imputed missing values using mean (for numeric) and mode (for categorical).
- Standardized labels and ensured consistent data types.
- Defined the target variable Exited (1 = churned, 0 = retained).

### Exploratory Data Analysis (EDA):
!https://postimg.cc/BPq1Vhb2
- Class imbalance is visible with fewer churned customers.
- Churned customers generally have lower credit scores, indicating financial risk.
- Higher churn is observed among customers aged 35–50.

### EDA Insights:

- Low balance or fewer active products correlate with higher churn rates.
- Geography and gender show moderate correlation with churn.
- Tenure and estimated salary have minimal impact.
### Feature Engineering

Categorical Features: Encoded using OneHotEncoder (Gender, Geography).

Continuous Variables: Scaled using StandardScaler.

Data Split: 80/20 into training and testing sets.

### Model Evaluation

### Key Metrics:
- Accuracy: ~86%
- Precision: ~84%
- Recall: ~79%
- F1-Score: ~81%
  
### Feature Importance:

CreditScore, Balance, Age, and NumberOfProducts are the strongest predictors of churn.

## Model Interpretation

### Key Insights:

- Credit behavior and customer engagement are more indicative of churn risk than demographics.
- The model can be used to target high-risk customers for retention efforts.

### Conclusion

- `Summary:` The model achieved strong accuracy and is interpretable.

`Key Findings:`

- Middle-aged customers with low credit scores or low engagement are more likely to churn.

- Focus retention strategies on these groups with loyalty incentives and credit management education.

## Further Analysis

`Model Enhancement:` Explore XGBoost or LightGBM for potentially better performance.

`Segmentation:` Implement K-Means clustering for customer segmentation.

`Real-Time Alerts:` Develop a churn alert system integrated with CRM data.

`Model Explainability:` Use SHAP analysis for deeper model interpretation.
