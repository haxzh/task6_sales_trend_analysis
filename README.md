# Task 6: Sales Trend Analysis Using Aggregations

## Objective
Analyze monthly revenue and order volume from the `orders` dataset.

## Dataset
Sample `orders` table with columns:
- `order_id`
- `order_date`
- `amount`
- `product_id`

File: `orders_sample.csv`

## Queries

### 1. Monthly Revenue and Order Volume
```sql
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM orders
GROUP BY year, month
ORDER BY year, month;
