
# 📊 Sales Insights Data Analysis

This project provides comprehensive sales analytics using SQL and Power BI. It focuses on extracting business insights from transactional data for the fictional retail company **AtliQ Hardware**.

---

## 📁 Project Structure

```
.
├── Sales Insights data analysis-AtliQ.pbix      # Power BI Dashboard file
├── sales_insights.sql                           # Base queries for transactional insights
└── sales_SQL_analysis.sql                       # Detailed analytical queries with temporal filters
```

---

## 📌 Objective

The goal of this project is to:

- Analyze **sales trends** over time (monthly/yearly).
- Compare revenue and product sales across **different markets** (e.g., Chennai, Mumbai).
- Determine key metrics like **total revenue, average sales, and maximum sales**.
- Build a dynamic and interactive **dashboard using Power BI** to visualize the outcomes.

---

## 🔍 Data Overview

- **Tables Used:**
  - `sales.transactions`
  - `sales.date`

- **Key Columns:**
  - `order_date`, `market_code`, `currency`, `sales_amount`, `product_code`

---

## 🧠 Key Insights and Queries

Here are some of the major queries and insights extracted:

- **Transactions filtered by market**:  
  ```sql
  SELECT * FROM sales.transactions WHERE market_code='Mark001'; -- Chennai
  ```

- **Total Revenue by Year**:  
  ```sql
  SELECT SUM(sales.transactions.sales_amount)
  FROM sales.transactions
  JOIN sales.date ON transactions.order_date = date.date
  WHERE sales.date.year = 2020 AND currency IN ('INR', 'USD');
  ```

- **Monthly Revenue Analysis by Market**:  
  ```sql
  SELECT SUM(transactions.sales_amount)
  FROM sales.transactions
  JOIN sales.date ON transactions.order_date = date.date
  WHERE year = 2020 AND month_name = 'January' AND market_code = 'Mark001';
  ```

These and other queries help analyze **regional performance** and **currency impact** on revenue.

---

## 📈 Power BI Dashboard

The Power BI file (`.pbix`) contains:

- **Interactive visuals** for revenue, sales count, and product performance
- **Filters for year, month, and market**
- **Comparative charts** across Chennai and Mumbai markets

---

## 🛠️ Tools Used

- **SQL** – Data extraction and transformation
- **Power BI** – Interactive dashboard and visualization
- **MySQL/PostgreSQL** – Assumed database environment

---

## 📌 Author

- **Vaishnavi Karingala**  
  [LinkedIn](https://www.linkedin.com) | [Email](mailto:vkaringala@horizon.csueastbay.edu)
