# coffeeshop-revenue-analysis

## Project Overview

This project analyzes a dataset of daily coffee shop operations to understand the main drivers of daily revenue. The dataset contains **2,000 observations** of **7 variables** including:


- Number of customers per day
- Average order value
- Daily marketing spend
- Operating hours
- Number of employees
- Location foot traffic
- Daily revenue

The goal is to identify which variables most strongly influence daily revenue and quantify their impact using a regression analysis.

* * *

## Exploratory Analysis

### 1. Correlation Analysis

- A correlation heatmap was created to assess linear relationships among all variables.
- Only correlations with |r| > 0.1 were highlighted as potentially meaningful for exploration, while smaller correlations were considered negligible.

**Key findings:**

- `Number_of_Customers_Per_Day` (r ≈ 0.736) and `Average_Order_Value` (r ≈ 0.536) are strong predictors of revenue.
- `Marketing_Spend_Per_Day` (r ≈ 0.255) is weaker, but still above the threshold.
- All other variables have correlations far below |0.1| and are unlikely to meaningfully improve revenue predictions.

### 2. Scatterplots & Regression Lines

- Scatterplots with regression lines were created for the three main predictors vs. daily revenue:
    - Number of customers → Daily revenue
    - Average order value → Daily revenue
    - Marketing spend → Daily revenue
- These visuals confirm that the relationships are linear and that average order value and number of customers are the strongest drivers.

* * *

## Linear Regression Analysis

A linear regression model was fit using the three key predictors:

Variables: Number_of_Customers_Per_Day, Average_Order_Value, Marketing_Spend_Per_Day  
Target: Daily_Revenue

**Results:**

- Coefficients:
    - Number of Customers: +5.57 per customer
    - Average Order Value: +243.30 per $1
    - Marketing Spend: +1.55 per $1
- Intercept: -1525.68
- R²: 0.891 (89% of day-to-day variation in revenue explained by these variables)

**Interpretation:**

- Each additional customer increases revenue by $5.57, holding other factors constant.
- Each $1 increase in average order value increases revenue by $243.30, holding other factors constant.
- Marketing expenditure has minimal per-dollar impact compared to customers or order value.
- To match the impact of a $1 increase in average order value, approximately **44 additional customers** would be needed.

* * *

## Business Takeaways

- Increasing average order value has a **substantially larger impact on revenue** than marketing spend or additional customers.
- Optimizing marketing or operational costs can save money without hurting revenue, but won’t increase it.
- The dataset does not include additional factors that might drive customers or order value (e.g., promotions, seasonality, menu changes, weather, competitor activity, demographics).

* * *

## Questions / Next Steps

- Does each row represent a single day for one shop, or are multiple shops included?
- Is daily marketing expenditure measured per shop or across multiple locations?
- Could additional data on promotions, seasonality, or customer demographics improve revenue prediction?

* * *

**Conclusion:**  
From this dataset, the strongest levers for revenue are **average order value** and **number of customers per day**, while marketing spend is a minor driver. Additional data would be needed to identify actionable strategies for increasing customer volume or order value.
