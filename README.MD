 📊 Task 6 - Sales Trend Analysis Using Aggregations

 🧑‍💻 Internship Task - Data Analyst Role

This task focuses on analyzing monthly revenue and order volume using SQL aggregation techniques with SQLite.

---

 🎯 Objective

Analyze sales data stored in the `online_sales` table to:
- Calculate **monthly revenue**
- Calculate **monthly order volume**
- Identify the **top 3 months** by total revenue

---

🛠️ Tools Used

- **SQLite** (via DB Browser for SQLite)
- SQL (Structured Query Language)
- GitHub for submission

---

 🧱 Table Structure

The `online_sales` table contains:

| Column Name  | Type    | Description                      |
|--------------|---------|----------------------------------|
| order_id     | INTEGER | Unique order ID                  |
| order_date   | TEXT    | Date of the order (YYYY-MM-DD)   |
| amount       | REAL    | Revenue amount for the order     |
| product_id   | INTEGER | ID of the product sold           |

---

 📌 Steps Performed

1. Created the `online_sales` table with appropriate columns.
2. Inserted 30 sample records spanning different months.
3. Wrote SQL queries to:
   - Analyze monthly revenue and order volume
   - Find the top 3 revenue-generating months

---

 💻 SQL Queries Used

 1️⃣ Monthly Revenue and Order Volume

```sql
SELECT
  STRFTIME('%Y', order_date) AS year,
  STRFTIME('%m', order_date) AS month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS order_volume
FROM
  online_sales
GROUP BY
  year, month
ORDER BY
  year, month;
