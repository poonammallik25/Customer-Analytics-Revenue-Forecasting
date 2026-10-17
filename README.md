# End-to-End Customer Analytics & Revenue Forecasting using Python

## Project Overview
A subscription-based digital services company wants to understand customer behavior, improve revenue and reduce churn. This project cleans raw customer data, engineers features, analyzes revenue and churn patterns, and builds a Linear Regression model to predict customer revenue.

## Tools Used
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Google Colab

## Dataset
Practice dataset provided during training: 2,560 records and 15 columns (customer details, subscription plan, usage, support tickets, marketing channel, churn and total revenue).

## Project Steps
1. **Data understanding:** shape, data types, missing values
2. **Data cleaning:** removed 60 duplicates, filled missing values (median for numeric columns, "Unknown" for city), converted dates to datetime, corrected 852 records where last active date was before signup date
3. **Feature engineering:** created 14 features including tenure in years, revenue per month, churn flag, age group, high-value customer flag, support intensity, plan rank and engagement score
4. **Exploratory analysis:** 14 visualizations (distributions, plan, channel and city comparisons, trends, correlation heatmap, model performance)
5. **Modeling:** Linear Regression with an 80/20 train-test split, evaluated using R², MAE and RMSE, then improved with an interaction feature

## Key Findings
- About 23% of customers have churned.
- Tenure (correlation 0.79) and monthly fee (0.52) are the main drivers of revenue.
- Standard plan has the lowest churn (~21%); Premium has the highest (~27%).
- Organic customers bring the highest average revenue; Mumbai contributes the most total revenue.
- Monthly signups peaked in mid-2021 and have declined since.
- Model 1 (7 features) reached R² ≈ 0.90 but showed a curved error pattern. Adding a monthly_fee × tenure interaction feature raised R² to ≈ 0.99999.

## Limitations
- Date errors were fixed by swapping dates, assuming a data-entry mistake.
- Revenue by month uses signup month because payment dates are unavailable.
- Revenue is almost exactly fee × tenure in this dataset, so the near-perfect R² may not hold on real-world data.

## Files
- `Customer_analytics__Revenue_Forcasting.ipynb`: full analysis notebook
- `cleaned_customer_data.csv`: cleaned dataset with engineered features
- `subscription_data - subscription_data.csv`: original dataset
