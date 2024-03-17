# MeriSkill Data Analyst Projects
My two projects from MeriSkill: Sales Analysis and HR Atrittion.
## Sales Analysis Project
Findings from my recent sales analysis project. The main objective was to examine sales data in order to pinpoint patterns, top-selling products, and revenue metrics that can inform strategic business decisions.

Sales Analysis Dashboard and Report Summary:

1. Total Revenue: Total revenue of $34.49 million was generated during the analysed period, indicating a strong sales performance.
2. Total Quantity Ordered: A total of 209,079 orders were processed, demonstrating substantial customer demand.
3. Unique Orders: There were 178,437 unique orders, showcasing a diverse and engaged customer base.
4. Monthly Sales Trend: December had the highest sales, while January had the lowest, providing valuable insights for future planning and strategy. Orders and sales peaked between 10 am and 8 pm.
5. Sales by City: San Francisco had the highest sales, contributing $8.23 million to the total revenue.
6. Top Product by Sales: The MacBook Pro Laptop was the top-selling product, generating $8,037,600 in revenue.
7. Quantity Ordered by Product: The 'AAA Batteries (4-pack)' was the top-selling product by quantity, with 31,017 units sold.

This analysis provides valuable insights into the company's sales performance and highlights areas for potential growth.

Tools used:
1. MS Excel: for reading and understanding data, ensuring data completeness, removing duplicates, and comparing with the Power BI dashboard.
2. MS Power BI (including Power Query & DAX): to remove redundant columns, split and rename columns, ensure correct data types for columns, create visualisations, and develop the dashboard.
## HR Atrittion
The objective of this project is to develop a comprehensive HR employee attrition dashboard using Power BI, aimed at providing insights into employee demographics, turnover analysis, and employee wellness. The dashboard, consisting of five pages, is designed to address various aspects of HR analytics:

1. HR Employee Attrition Overview (Page 1): This page acts as an introduction to the dashboard, giving a brief overview of the subsequent pages and their respective analyses. This page, along with others, utilizes navigation buttons to facilitate access to any page from every page.

2. Demographics Report (Page 2): This page delves into a detailed breakdown of employee demographics, showcasing attrition rates categorized by age group, gender, marital status, and other relevant factors. I utilized the DAX function to create new columns and measures for enhanced analysis accuracy.

3. Turnover Analysis 1 (Page 3): Page 3 provides a deeper dive into turnover analysis, presenting key insights and trends related to employee attrition. I crafted insightful visualizations to display turnover rates, reasons for attrition, and areas for potential improvement.

4. Turnover Analysis 2 (Page 4): Expanding on the analysis from Page 3, Page 4 offers additional insights into turnover patterns and identifies underlying factors contributing to attrition.

5. Employee Wellness (Page 5): The final page concentrates on employee wellness, offering insights into factors that impact employee satisfaction and well-being.

This HR employee attrition dashboard not only delivers a comprehensive overview of attrition trends but also provides actionable insights for HR professionals to optimize employee retention strategies and enhance organizational effectiveness.
## SQL Questions
1. Table: sales (columns: date, product_id, revenue).
   Question: Calculate the total revenue for each product in the year 2023.
   SQL query:
   
   * SELECT product_id, SUM(revenue) AS total_revenue
   - FROM sales
   + WHERE YEAR(date) = 2023
   * GROUP BY product_id;

2. Tables: employees (columns: employee_id, department_id, salary); departments (columns: department_id, department_name).
   Question: What is the average salary for each department?
   SQL query:

   * SELECT d.department_name, AVG(e.salary) AS avg_salary
   - FROM employees e
   + JOIN departments d ON e.department_id = d.department_id
   * GROUP BY d.department_name;

3. Table: orders (columns: order_id, customer_id, order_date, order_total).
   Question: Who are the top 5 customers who spent the most in total?
   SQL query:

   * SELECT customer_id, SUM(order_total) AS total_spent
   - FROM orders
   + GROUP BY customer_id
   * ORDER BY total_spent DESC
   - LIMIT 5;

4. Table: transactions (columns: transaction_id, transaction_date, amount, transaction_type).
   Question: Total amount of purchases made in each month of the year 2023.
   SQL query:

   * SELECT MONTH(transaction_date) AS month, SUM(amount) AS total_purchases
   - FROM transactions
   + WHERE YEAR(transaction_date) = 2023 AND transaction_type = 'purchase'
   * GROUP BY MONTH(transaction_date);

5. Table: products (columns: product_id, product_name, price).
   Question: What are the top 3 most expensive products?
   SQL query:

   - SELECT product_id, product_name, price
   * FROM products
   + ORDER BY price DESC
   - LIMIT 3;
