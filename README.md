## Project Title:
# Customer Churn Analysis in Banking: Insights & Predictive Modelling
### Project Description
This project focuses on analyzing customer churn data for a retail bank to identify the factors driving customer attrition and to build a predictive model that classifies customers as likely to churn or stay. The analysis combines data cleaning, exploratory data analysis (EDA), and machine learning classification techniques to uncover actionable insights for improving customer retention.
## Objectives:
- `Import & Validate Data:`Import and quality-check two customer data tables.
- `Data Preprocessing:`Clean, merge, and prepare the data for analysis.
- `Exploratory Data Analysis (EDA):`Analyze churn patterns to uncover insights.
- `Model Development:` Build a predictive classification model to estimate churn probability.
- `Model Interpretation & Insights:` Interpret model results and translate them into actionable business insights.

### Data Preparation and Cleaning:
-  Our first objective is to Import & Join two customer Data Tables, then Remove Duplicate Rows & Columns       and Fill in Missing Values.
-  Our Second Objective is to Clean the Data by fixing inconsistencies in labeling, handling erroneous          values, and fixing currency fields.
-  Some libraries are used for data manipulation, numerical computations, and visualization.
-  Data from two sheets are read — one for customer demographics and another for account-level details.
-  Datasets are merged on the CustomerId column to create a unified dataset.

## Data Cleaning Steps:

- Removed duplicates and irrelevant columns.
- Imputed missing values using mean (for numeric) and mode (for categorical).
- Standardized labels and ensured consistent data types.
- Defined the target variable Exited (1 = churned, 0 = retained).

### Exploratory Data Analysis (EDA):
1. Our third objective is to explore the target variable (Exited) and look at feature-target relationships      for categorical and numeric fields:

  2. Building a bar chart displaying the count of churners (Exited=1) vs. non-churners (Exited=0).
  3. Exploring the categorical variables vs. the target, and look at the percentage of Churners by                “Geography” and “Gender”.
  4. Building box plots for each numeric field, broken out by churners vs. non-churners.
  5. Building histograms for each numeric field, broken out by churners vs. non-churner



### EDA Insights:
[![pairplot.png](https://i.postimg.cc/mg0yQT8d/pairplot.png)](https://postimg.cc/0z0Sv1gm)

[![Correlation.png](https://i.postimg.cc/cC3M62Nk/Correlation.png)](https://postimg.cc/BPq1Vhb2)

- Low balance or fewer active products correlate with higher churn rates.
- Geography and gender show moderate correlation with churn.
- Tenure and estimated salary have minimal impact.
### Feature Engineering
Our final objective is to prepare the data for modeling through feature selection, feature engineering, and data splitting:

- Creating a new dataset that excludes any columns that aren’t be suitable for modeling.

- Creating Dummy Variables for categorical fields.

- Create a new “balance_v_income” feature, which divides a customer’s bank balance by their estimated salary, then visualize that feature vs. churn status

- Categorical Features: Encoded using OneHotEncoder (Gender, Geography).


### For Model Evaluation

- Continuous Variables: Scaled using StandardScaler.

- Data Split: 80/20 into training and testing sets.
- Finding
[![ROC.png](https://i.postimg.cc/W3SZfVwh/ROC.png)](https://postimg.cc/k66DBkZm)
[![Pecall.png](https://i.postimg.cc/RFP3LRv0/Pecall.png)](https://postimg.cc/TLDYRnL8)
  
### Key Metrics:
- Accuracy: ~86%
- Precision: ~84%
- Recall: ~79%
- F1-Score: ~81%
  
### Feature Importance:

[![important-feature.png](https://i.postimg.cc/SR2K7bZ1/important-feature.png)](https://postimg.cc/kRC9qzPW)

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
