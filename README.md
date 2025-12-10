# Fintech-App-Project
Python, SQL, PowerBI,  Excel, Predictive-Modeling, EDA,

# Product Usage & Retention Analytics Dashboard for a Fintech App
## Project Summary
This project focuses on building a comprehensive analytics pipeline and dashboard for a fintech company operating in Sub-Saharan Africa. The company offers microloans, savings, and bill payment services through its app. The product team is interested in understanding user behavior, retention trends, churn risks, and feature engagement to drive growth and product decisions.

The goal of this project is to create a data-driven Product Analytics Dashboard that allows the team to monitor key metrics, identify at-risk users, and make strategic decisions based on actionable insights.

## Objectives
- Track Daily Active Users (DAU) and Monthly Active Users (MAU)
- Identify which user segments are likely to churn or remain active
- Analyze feature engagement across microloans, bill payments, and transfers
- Generate retention curves and cohort analyses to understand user lifecycle
- Provide insights that can be easily communicated to the product and marketing teams

## Tools & Technologies
| Category | Tools |
|----------|-------|
| Data Storage & Queries | SQL / PostgreSQL |
| Data Cleaning & EDA | Python (Pandas, NumPy, Matplotlib, Seaborn) |
| Visualization | Power BI |
| Predictive Modeling | Logistic Regression, Random Forest |
| Documentation & Reporting | Excel, Google Slides |
| Dataset Source | Anonymized user data exported from the fintech app |

## Project Pipeline

### 1. Data Cleaning & Pre-Analysis
- Imported the anonymized user dataset using Python.
- Cleaned and transformed columns such as `Total_Transactions`, `Avg_Transaction_Value`, `Total_Spent`, `Active_Days`, and `Preferred_Payment_Method`.
- Created a `Churn` column using a defined threshold on `Active_Days` to indicate inactive or at-risk users.
- Explored missing values, summary statistics, and distributions to understand the data.

**Sample Cleaned Data:**

| user_id   | Total_Transactions | Avg_Transaction_Value | Total_Spent | Active_Days | Preferred_Payment_Method | Churn |
|-----------|------------------|---------------------|------------|-------------|-------------------------|-------|
| cust_0000 | 192              | 16736.38            | 3,213,386  | 140         | Debit Card             | 0     |
| cust_0001 | 979              | 14536.73            | 14,231,460 | 229         | UPI                    | 0     |
| cust_0002 | 329              | 7061.37             | 2,323,192  | 73          | Debit Card             | 1     |
| cust_0003 | 71               | 16426.87            | 1,166,308  | 299         | Wallet Balance         | 0     |
| cust_0004 | 878              | 10800.09            | 9,482,481  | 236         | UPI                    | 0     |


### 2. Exploratory Data Analysis (EDA)
- Conducted descriptive statistics on numeric and categorical columns.
- Visualized distributions of transactions, spending, and active days.
- Analyzed churn patterns across different user segments and payment methods.
- Created visualizations using Matplotlib and Seaborn to identify key trends.

### 3. Predictive Modeling
**Objective:** Predict the likelihood of a user churning based on transaction and behavioral patterns.

**Approach:**
- Features: `Total_Transactions`, `Avg_Transaction_Value`, `Total_Spent`, `Active_Days`, `Preferred_Payment_Method`
- Target: `Churn` (0 = active, 1 = churned)
- Categorical feature (`Preferred_Payment_Method`) was one-hot encoded.
- Numeric features were scaled using `StandardScaler`.
- Train-test split: 80% training, 20% testing, stratified by churn.

**Models Used:**
- Logistic Regression
- Random Forest Classifier

**Performance Metrics:**

**Logistic Regression**
- Accuracy: 0.98
- Precision, Recall, F1-score: high for both churned and active users
- ROC AUC: 1.0

**Random Forest**
- Accuracy: 1.0
- Precision, Recall, F1-score: perfect classification
- ROC AUC: 1.0

*The models successfully identify users at risk of churn, enabling targeted retention strategies.*

### 4. Power BI Dashboard
- Integrated cleaned dataset into Power BI.
- Key visualizations:
  - DAU & MAU trends
  - Churn by user segment
  - Feature engagement across app functionalities
  - Cohort retention curves
- The `.pbix` file is included in the repository under `/powerbi`.
- A screenshot of the dashboard is available in `/images/dashboard_screenshot.png`.

### 5. Next Steps
- Build KPI tracking sheets in Excel to monitor performance over time.
- Prepare a report/presentation in Google Slides for stakeholders.
- Expand predictive modeling to include other behavioral metrics such as feature usage frequency.
- Enhance Power BI dashboard interactivity with filters, drill-downs, and trend analyses.

## Repository Structure
- data/
  - product_analytics database on MySQL
- notebooks/
  - 01_product_analytics_EDA.ipynb
  - 02_predictive_modeling.csv
- powerbi/
  - CrediLink_Dashboard.pbix
- images/
  - dashboard_screenshot.png


