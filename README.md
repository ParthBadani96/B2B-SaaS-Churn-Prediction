B2B SaaS Churn Prediction Project

Overview

This project focuses on predicting customer churn for a B2B SaaS company using machine learning techniques and visualizing actionable insights in Power BI. The goal is to identify at-risk customers, understand the drivers of churn, and provide recommendations to reduce churn and increase revenue.


The primary objective of this project is to:

Predict customer churn using machine learning models.
Identify key factors contributing to churn.
Provide actionable insights to reduce churn and improve customer retention.
Visualize churn-related metrics and trends for business stakeholders.
Dataset and Data Sources
The dataset was generated and processed to simulate real-world B2B SaaS customer behavior. It includes the following key columns:


Customer Details

CUSTOMER_ID: Unique identifier for each customer.
SEGMENT: Customer segment (e.g., SMB, Mid-Market, Enterprise).
INDUSTRY: Industry of the customer.
COUNTRY: Customer's country.
Subscription Details
PLAN: Subscription plan (e.g., Basic, Premium, Enterprise).
SUBSCRIPTION_DURATION: Duration of the subscription in months.
MRR: Monthly Recurring Revenue.
Usage Metrics
AVG_MONTHLY_LOGINS: Average monthly logins by the customer.
AVG_TICKETS_RAISED: Average number of support tickets raised.
AVG_FEATURE_USAGE: Average feature usage score.
Churn Prediction
ACTUAL_CHURN: Whether the customer churned (1) or not (0).
PREDICTED_CHURN: Model's prediction of churn.
CHURN_PROBABILITY: Probability of churn predicted by the model.
RISK_LEVEL: Categorized churn risk (Low, Medium, High).
REVENUE_AT_RISK: Revenue at risk due to potential churn.


Project Workflow

The project was executed in the following steps:

1. Data Generation
Synthetic data was generated using Python libraries (pandas, numpy, random) to simulate customer behavior.
The data was saved into CSV files:

customer_accounts.csv
subscriptions.csv
usage_metrics.csv


2. Data Upload to Snowflake
The generated CSV files were uploaded to Snowflake using:
Snowflake Web Interface: For staging and loading data.
SQL Queries: To create tables and load data into Snowflake.


3. Feature Engineering
SQL queries were used to engineer features such as:

Subscription duration.
Revenue at risk.
Aggregated usage metrics.
Null values were handled, and active subscriptions were calculated using the current date.


4. Modeling
The feature-engineered dataset was exported from Snowflake and loaded into a Jupyter Notebook.
Steps:

Data Preprocessing:
Handled missing values.
Encoded categorical variables.
Scaled numerical features.
Class Imbalance Handling:
Used SMOTE (Synthetic Minority Oversampling Technique) to balance the dataset.

Model Training:
Trained multiple models, including Logistic Regression.

Evaluation:
Evaluated models using metrics like accuracy, precision, recall, and F1-score.


5. Visualization
The final dataset, including predictions, was uploaded to Power BI for visualization.
Key metrics and trends were visualized to provide actionable insights.



Tools and Libraries Used

1. Python Libraries
pandas, numpy: Data manipulation and analysis.
scikit-learn: Machine learning and evaluation.
imbalanced-learn: SMOTE for handling class imbalance.
matplotlib, seaborn: Data visualization.


2. Snowflake
SQL for querying, feature engineering, and data export.


3. Power BI
For creating interactive dashboards and visualizations.
Modeling Insights


Best Model: SMOTE achieved the highest performance with an accuracy of 95%.


Key Features Driving Churn:

Low feature usage.
Short subscription durations.
Low monthly logins.


Class Imbalance: Addressed using SMOTE, which improved model performance by ensuring balanced training data.


Revenue at Risk: Identified high-risk customers contributing to significant revenue loss.


Visualizations and Insights
The following visualizations were created in Power BI:

1. Churn Distribution
Visualization: Bar chart.
Insight: Shows the proportion of churned vs. non-churned customers.

2. Churn by Segment
Visualization: Stacked bar chart.
Insight: Growth customers have the highest churn rate.

3. Revenue at Risk by Country
Visualization: Tree map.
Insight: The USA and UK contribute the most to revenue at risk.

4. Risk Level Breakdown
Visualization: Pie chart.
Insight: 30% of customers are in the high-risk category.

5. Feature Usage vs. Churn
Visualization: Scatter plot.
Insight: Customers with low feature usage are more likely to churn.


Business Recommendations

1. Target High-Risk Customers:
Focus retention efforts on customers in the high-risk category.
Offer incentives or personalized support to reduce churn.

2. Improve Feature Adoption:
Educate customers on underutilized features.
Provide training sessions or tutorials.

3. Monitor Key Metrics:
Track monthly logins and feature usage to identify at-risk customers early.

4. Optimize Subscription Plans:
Offer flexible plans to retain customers with short subscription durations.

Final Dataset: data/final_dataset.csv
