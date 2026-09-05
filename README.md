# Northwind Customer & Revenue Analysis

Customer segmentation, churn risk, and revenue analysis on the Northwind sample database — built with SQL for data extraction and business logic, and Tableau for interactive visualization.

**Live Dashboard:** [View on Tableau Public][https://public.tableau.com/views/NorthwindCustomerRevenueAnalysis/NorthwindCustomerRevenueAnalysis?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link]

<img width="1710" height="1070" alt="Screenshot 2026-09-04 at 11 09 26 PM" src="https://github.com/user-attachments/assets/dd616757-6508-4142-9e1c-ec83b442eee0" />


## Project Overview

This project analyzes customer purchasing behavior using an RFM (Recency, Frequency, Monetary) framework, then translates those findings into an interactive Tableau dashboard. It was built in two stages:

1. **SQL Analysis** — querying the Northwind database to calculate customer spend, order frequency, recency, churn risk, and product performance
2. **Tableau Dashboard** — visualizing those findings, with several metrics (churn threshold, spend tiers) rebuilt natively in Tableau using calculated fields, rather than just importing pre-computed SQL results

## Files

- `northwind_customer_analysis.sql` — full SQL script with business questions and queries
- `Northwind Customer & Revenue Analysis.twbx` — packaged Tableau workbook
- `customer_rfm.csv`, `top_products_revenue.csv`, `top_products_units.csv`, `revenue_by_year.csv` — exported query results used in Tableau

## Dashboard Highlights

- **Top 10 Customers** — highlighted table by total spend
- **Customers at Risk of Churning** — customers flagged using a days-since-last-order threshold
- **Top 10 Products by Revenue** — rebuilt in Tableau using a calculated field, joining OrderDetails and Products
- **Customer Value vs. Churn Risk** — scatter plot with Tableau's built-in clustering
- **Customer Spend Tier Segmentation** — treemap segmenting customers into Low/Medium/High spend tiers

## Key Findings

- A small group of 17 "High Spend" customers averages **$5.48M** in spend each — individually more valuable than the larger "Medium Spend" group (65 customers, averaging $4.76M each), even though Medium Spend drives more *total* revenue overall.
- 5 customers were flagged as at-risk of churning based on a recency threshold, with the longest-dormant customer having gone quiet for over 170 days relative to the dataset's most recent order.
- Revenue-driving products are far more concentrated than best-selling products by volume — the top product by revenue outsells the next closest competitor by more than 2x, while unit sales across the top 10 products are comparatively flat.

## Tools Used

SQLite / DB Browser for SQLite, Tableau Public Desktop
