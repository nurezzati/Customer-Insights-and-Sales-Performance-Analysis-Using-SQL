# Customer-Insights-and-Sales-Performance-Analysis-Using-SQL

📊 Overview<br>
This project demonstrates end-to-end SQL-based data analytics, covering both Exploratory Data Analysis (EDA) and Advanced Analytics. The analysis is designed to extract key insights about customer behavior, sales trends, and business performance using SQL.

🔍 1. Exploratory Data Analysis (EDA)
EDA focuses on understanding the data — its structure, patterns, and key metrics.

| Step                          | Focus Area                                                    | Description                                                                                                              | Example SQL Task                                                               |
| ----------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| **1. Database Exploration**   | Understand available tables and relationships                 | Inspect schema and table structures                                                                                      | `SELECT * FROM INFORMATION_SCHEMA.TABLES;`                                     |
| **2. Dimensions Exploration** | Explore dimension tables like customers, products, or regions | Identify unique values and categories                                                                                    | `SELECT DISTINCT region FROM dim_customers;`                                   |
| **3. Date Exploration**       | Analyze time-based data                                       | Extract trends by month, quarter, or year                                                                                | `SELECT YEAR(order_date), COUNT(*) FROM fact_sales GROUP BY YEAR(order_date);` |
| **4. Measures Exploration**   | Examine key numerical fields                                  | Check ranges, averages, and outliers                                                                                     | `SELECT AVG(sales_amount), MAX(sales_amount) FROM fact_sales;`                 |
| **5. Magnitude**              | Identify largest/smallest contributors                        | Rank sales by customer or product                                                                                        | `ORDER BY total_sales DESC;`                                                   |
| **6. Ranking**                | Find top-N and bottom-N performers                            | `SELECT TOP 10 customer_name, SUM(sales_amount) FROM fact_sales GROUP BY customer_name ORDER BY SUM(sales_amount) DESC;` |                                                                                |

🚀 2. Advanced Analytics
After understanding the data, advanced analysis provides deeper business insights.

| Step                             | Analysis Type                                | Description                         | Example SQL Calculation                                |
| -------------------------------- | -------------------------------------------- | ----------------------------------- | ------------------------------------------------------ |
| **7. Change-Over-Time (Trends)** | Analyze growth/decline trends                | Monthly or yearly comparisons       | `LAG` / `LEAD` window functions                        |
| **8. Cumulative Analysis**       | Track running totals or progress             | Cumulative sales or revenue         | `SUM(sales_amount) OVER (ORDER BY order_date)`         |
| **9. Performance Analysis**      | Assess KPIs like customer retention or spend | Customer segment classification     | CASE WHEN + aggregation                                |
| **10. Part-to-Whole Analysis**   | Understand proportions or shares             | % contribution of each segment      | `(sales_amount / total_sales) * 100`                   |
| **11. Data Segmentation**        | Group customers or products                  | Based on spending, age, or activity | `CASE WHEN lifespan >= 12 THEN 'Loyal' ELSE 'New' END` |
| **12. Reporting**                | Summarize insights for dashboards            | Create final views for BI tools     | `CREATE VIEW report_customers AS ...`                  |

🛠️ Tools Used
SQL Server Management Studio (SSMS)

💡 Key Learnings
Designing reusable SQL views for business reporting
Translating analytical logic into SQL
Performing EDA and advanced analysis without external tools

