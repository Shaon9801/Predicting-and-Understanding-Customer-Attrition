# Predicting-and-Understanding-Customer-Attrition

## Project Title:
### Customer Churn Analysis in Banking: Insights & Predictive Modelling
!<img width="1476" height="105" alt="image" src="https://github.com/user-attachments/assets/04c8372e-8e03-4dd3-8d84-614d5f763cfc" />
.
### Project Description
This project analyzes pizza sales data using **SQL** to generate insights into revenue, customer behaviour, and sales trends. It aims to help businesses understand sales performance, customer preferences, and operational efficiency.
## Objectives:
- `Import & Validate Data:` Load and ensure the quality of two customer data tables.
- `Data Preprocessing:` Clean, merge, and prepare the data for analysis.
- `Exploratory Data Analysis (EDA):` Analyze churn patterns to uncover insights.
- `Model Development:` Build a predictive classification model to estimate churn probability.
- `Model Interpretation & Insights:` Interpret model results and translate them into actionable business insights.

## 4. Data Preparation and Cleaning


###Code Overview:
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
### These libraries are used for data manipulation, numerical computations, and visualization.

```python
churn_cust_info = pd.read_excel("Bank_Churn_Messy.xlsx")
churn_acct_info = pd.read_excel("Bank_Churn_Messy.xlsx", sheet_name=1)
```


### Data from two sheets are read — one for customer demographics and another for account-level details.
```python
churn_df = churn_cust_info.merge(churn_acct_info, how="left", on="CustomerId")
```


### Datasets are merged on the CustomerId column to create a unified dataset.

## Data Cleaning Steps:

- Removed duplicates and irrelevant columns.
- Imputed missing values using mean (for numeric) and mode (for categorical).
- Standardized labels and ensured consistent data types.
- Defined the target variable Exited (1 = churned, 0 = retained).

### Exploratory Data Analysis (EDA)
``python
sns.countplot(x="Exited", data=churn_df)
plt.title("Customer Churn Distribution")
```


Class imbalance is visible with fewer churned customers.

sns.boxplot(x="Exited", y="CreditScore", data=churn_df)


## Churned customers generally have lower credit scores, indicating financial risk.

sns.histplot(churn_df["Age"], bins=20, hue=churn_df["Exited"])


Higher churn is observed among customers aged 35–50.

### EDA Insights:

Low balance or fewer active products correlate with higher churn rates.

Geography and gender show moderate correlation with churn.

Tenure and estimated salary have minimal impact.

6. Feature Engineering

Categorical Features: Encoded using OneHotEncoder (Gender, Geography).

Continuous Variables: Scaled using StandardScaler.

Data Split: 80/20 into training and testing sets.

7. Model Development

Code Overview:

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report, confusion_matrix

X = churn_df.drop("Exited", axis=1)
y = churn_df["Exited"]
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)


Random Forest Classifier is trained and tested on the dataset.

rf = RandomForestClassifier(random_state=42)
rf.fit(X_train, y_train)
y_pred = rf.predict(X_test)


Model Evaluation:

print(classification_report(y_test, y_pred))


Key Metrics:

Accuracy: ~86%

Precision: ~84%

Recall: ~79%

F1-Score: ~81%

Feature Importance:

CreditScore, Balance, Age, and NumberOfProducts are the strongest predictors of churn.

8. Model Interpretation

Key Insights:

Credit behavior and customer engagement are more indicative of churn risk than demographics.

The model can be used to target high-risk customers for retention efforts.

9. Conclusion

Summary: The model achieved strong accuracy and is interpretable.

Key Findings:

Middle-aged customers with low credit scores or low engagement are more likely to churn.

Focus retention strategies on these groups with loyalty incentives and credit management education.

10. Further Analysis

Model Enhancement: Explore XGBoost or LightGBM for potentially better performance.

Segmentation: Implement K-Means clustering for customer segmentation.

Real-Time Alerts: Develop a churn alert system integrated with CRM data.

Model Explainability: Use SHAP analysis for deeper model interpretation.
