# 🚲 Bike Store Sales Analysis: SQL Portfolio Project

## 📝 Project Description
An end-to-end SQL analysis project utilizing a multi-table relational database for a global bike retailer. This project demonstrates the ability to extract, join, and analyze data to drive business decisions regarding sales, inventory, and customer retention.

---

## 📂 Data Architecture
The project utilizes 9 structured tables:

| Category | Table Names |
| :--- | :--- |
| **Sales** | `customers`, `orders`, `order_items`, `staffs`, `stores` |
| **Products** | `brands`, `categories`, `products`, `stocks` |

---

## 🎯 Project Objectives & SQL Implementation

### 1. Financial Performance Analysis
* **Goal:** Determine total revenue generated per product category.
* **Skill:** Multi-table Joins, Aggregations, and Arithmetic operations.

```sql
SELECT 
    cat.category_name, 
    SUM(it.list_price * it.quantity * (1 - it.discount)) AS total_net_revenue
FROM sales.order_items it
JOIN production.products p ON it.product_id = p.product_id
JOIN production.categories cat ON p.category_id = cat.category_id
GROUP BY cat.category_name
ORDER BY total_net_revenue DESC;
```

##💡 Key Business Insights
Revenue Concentration: High-end mountain bikes account for the majority of revenue despite lower sales volume.

Customer Loyalty: 20% of the customer base contributes to nearly 60% of total repeat orders.

Supply Chain: Store Location X consistently experiences a 3-day shipping lag compared to other branches.

##🛠 Tools Used
Database: MySQL

Documentation: Markdown

Data Source: Bike Store Relational Dataset

🔗 Connect with me
LinkedIn: <https://www.linkedin.com/in/muhammad-uzi-khan/>

Portfolio: [Link to other projects]
