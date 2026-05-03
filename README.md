# 📚 Bookstore Analytics System (SQL)

## 📌 Overview

The **Bookstore Analytics System** is a database-driven project designed to manage and analyze bookstore operations using SQL.
It focuses on extracting meaningful insights from sales, customer, and inventory data to support better business decisions.

---

## 🎯 Objectives

* Design a structured relational database for a bookstore
* Perform data analysis using SQL queries
* Generate insights like sales trends, top-selling books, and customer behavior

---

## 🛠️ Technologies Used

* **MySQL** – Database management
* **SQL** – Data querying and analysis

---

## 🗂️ Database Schema

### Tables:

* **Books** (`book_id`, `title`, `genre`, `price`, `stock`)
* **Customers** (`customer_id`, `name`, `city`,'signup_date')
* **Orders** (`order_id`, `customer_id`,'book_id','quantity', `order_date`)
* **Marketingspend** (`spend_id`, `customer_id`, `spend_amount`)

---

## 📊 Key Features

* 📈 Sales analysis (daily, monthly revenue)
* 📚 Identification of top-selling books
* 👤 Customer purchase tracking
* 📦 Inventory monitoring (stock levels)
* 🔍 Advanced SQL queries using:

  * JOIN operations
  * GROUP BY
  * Aggregate functions
  * Subqueries

---

## 📈 Sample SQL Queries

### 🔹 Total Revenue

```sql
SELECT SUM(b.price * oi.quantity) AS total_revenue
FROM order_items oi
JOIN books b ON oi.book_id = b.book_id;
```

### 🔹 Top 5 Best-Selling Books

```sql
SELECT b.title, SUM(oi.quantity) AS total_sold
FROM order_items oi
JOIN books b ON oi.book_id = b.book_id
GROUP BY b.title
ORDER BY total_sold DESC
LIMIT 5;
```

### 🔹 Monthly Sales Analysis

```sql
SELECT DATE_FORMAT(order_date, '%Y-%m') AS month,
       COUNT(order_id) AS total_orders
FROM orders
GROUP BY month;
```

---

## 📊 Insights Generated

* Identified high-demand books based on sales volume
* Analyzed monthly revenue trends
* Detected frequent customers for targeted marketing

---

## ▶️ How to Run the Project

1. Create a database in MySQL
2. Execute `schema.sql` to create tables
3. Insert sample data using `data.sql`
4. Run queries from `analysis.sql`

---

## 📌 Future Enhancements

* Integration with Python for data visualization
* Development of a web-based dashboard (Flask/Django)
* Implementation of a recommendation system

---
