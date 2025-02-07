# 🚀 PostgreSQL Mini Challenge with Neon

Welcome to the **PostgreSQL Mini Challenge**! In this challenge, you'll use **Neon** to create a sample table, analyze the data, and write SQL queries to answer three analytical questions. Let's get started! 🎯

---

## **📌 Step 1: Sign Up for Neon**
If you haven’t signed up yet, follow these steps:

1. **Sign up for free** at 👉 [Neon Console](https://console.neon.tech/signup).
2. Use your **Email, GitHub, Google**, or other partner accounts to sign up.
3. For details about the free plan, check out **Neon Free Plan**.

---

## **📌 Step 2: Open SQL Editor in Neon Console**

1. Once logged in, navigate to the **SQL Editor** from the sidebar.
2. Your default branch (`main`) and the **neondb** database (created during onboarding) will be selected automatically.

---

## **📌 Step 3: Create & Populate the Table**
Copy and run the following SQL script in the **Neon SQL Editor** to create and populate a sample dataset:

```sql
CREATE TABLE sales (
    id SERIAL PRIMARY KEY,
    product_name VARCHAR(50),
    category VARCHAR(50),
    quantity_sold INT,
    sale_amount DECIMAL(10,2),
    sale_date DATE
);

INSERT INTO sales (product_name, category, quantity_sold, sale_amount, sale_date)
SELECT 
    'Product_' || (random() * 10)::INT + 1 AS product_name,
    CASE (random() * 3)::INT 
        WHEN 0 THEN 'Electronics' 
        WHEN 1 THEN 'Clothing' 
        ELSE 'Home Appliances' 
    END AS category,
    (random() * 20 + 1)::INT AS quantity_sold,
    (random() * 500 + 50)::DECIMAL(10,2) AS sale_amount,
    CURRENT_DATE - (random() * 30)::INT AS sale_date
FROM generate_series(1, 100);
```

---

## **📌 Step 4: View the Data in Neon Console**

1. Navigate to the **Tables** page in the Neon Console.
2. Select the **sales** table to view the inserted data.

---

## **📌 Step 5: Solve These 3 SQL Challenges**
Write SQL queries in the **SQL Editor** to answer the following questions:

### **1️⃣ Inventory Manager's Dilemma
The Inventory Manager at your company is trying to identify the most in-demand products to ensure stock availability. 
However, the raw data is overwhelming. Your task is to help them determine the top 3 products that customers purchased the most (by quantity sold) so they can optimize inventory planning.**


### **Finance Team's Revenue Breakdown
The Finance Team is preparing an internal report for stakeholders and needs a breakdown of sales across different product categories. They want to understand:

Which categories generate the highest revenue?
How much, on average, does a single sale contribute to revenue in each category?**

### **CEO’s Big Question
The CEO wants to know which day saw the highest revenue in the last 30 days, as they are considering running promotions around similar patterns. 
Instead of scanning through daily reports manually, they need a precise answer from the data.**

---

## 🎯 **Challenge Complete!**
Once you have your answers, take a screenshot and share it with the community. 🚀

