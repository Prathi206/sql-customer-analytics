# SQL Customer Analytics

## Overview
This project analyzes customer transaction data to identify revenue contribution, purchase behavior, and retention patterns using SQL.

## Business Objective
- Identify high-value customers
- Analyze revenue distribution
- Track monthly sales trends
- Segment repeat vs one-time customers

## Tools Used
- SQL (MySQL / SQL Server)
- Aggregations
- Window Functions
- CASE statements

## Dataset
Transactional data containing:
- customer_id
- order_id
- order_date
- revenue
- product_category

## Key Insights
- A small percentage of customers contributed a major share of total revenue.
- Repeat customers generated higher cumulative revenue compared to one-time buyers.
- Revenue trends showed variation across different months.
- Customers inactive for more than 90 days were identified as potential churn risk.

## Sample Analysis

### Revenue by Customer
```sql
SELECT customer_id, SUM(revenue) AS total_revenue
FROM orders
GROUP BY customer_id
ORDER BY total_revenue DESC;
```

### Customer Ranking
```sql
SELECT 
    customer_id,
    SUM(revenue) AS total_revenue,
    RANK() OVER (ORDER BY SUM(revenue) DESC) AS revenue_rank
FROM orders
GROUP BY customer_id;
```

## Conclusion
This project demonstrates the use of SQL to transform raw transactional data into actionable business insights.  
The analysis highlights customer revenue concentration, purchase behavior trends, and segmentation logic that can support data-driven decision-making.

