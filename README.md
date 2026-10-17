# Olist E-Commerce Business Intelligence Dashboard

## Project Overview

This project is a complete Business Intelligence dashboard built using Power BI on the Brazilian Olist E-Commerce dataset.

The dashboard analyzes:
- Revenue performance
- Customer behavior
- Delivery efficiency
- Product performance
- Seller contribution

The goal of this project is to transform raw e-commerce data into meaningful business insights through interactive dashboards and DAX-driven analytics.

---

# Business Problem

E-commerce businesses generate large amounts of transactional data, but raw data alone does not provide actionable insights.

This project helps answer important business questions such as:

- Which product categories generate the highest revenue?
- How do delivery delays affect customer satisfaction?
- What percentage of customers are repeat customers?
- Which sellers contribute most to marketplace revenue?
- How are customers distributed geographically?
- Which operational areas need improvement?

---

# Dataset Information

Dataset Source:
- Olist Brazilian E-Commerce Public Dataset

Tables Used:
- customers
- orders
- order_items
- order_payments
- order_reviews
- products
- sellers

Additional Tables Created:
- DateTable
- CustomerType
- DeliveryStatus

---

# Data Model

The dashboard was built using a star-schema style relationship model.

Key relationships were created between:
- Orders ↔ Customers
- Orders ↔ Order Items
- Orders ↔ Payments
- Orders ↔ Reviews
- Order Items ↔ Products
- Order Items ↔ Sellers
- Orders ↔ DateTable

---

# Dashboard Pages

## 1. Executive Overview

This page provides a high-level summary of marketplace performance.

### Key Metrics
- Total Revenue
- Total Orders
- Unique Customers
- Average Order Value
- Repeat Customer Rate
- Late Delivery Percentage

### Key Visuals
- Monthly Revenue Trend
- Top Product Categories by Revenue
- Category Filter
- Revenue KPIs

---

## 2. Customer Analytics

This page focuses on customer behavior and customer value analysis.

### Key Metrics
- Repeat Customers
- One-Time Customers
- Revenue Per Customer
- Top Customer Revenue

### Key Visuals
- Customer Retention Breakdown
- Customer Distribution by State
- Top Customers by Revenue
- Customer Growth Trend

### Business Insights
- Repeat customers form a very small percentage of the customer base
- Revenue contribution is concentrated among top customers
- Customers are heavily concentrated in southeastern Brazil

---

## 3. Delivery & Operations Analysis

This page analyzes operational efficiency and delivery performance.

### Key Metrics
- Average Delivery Days
- On-Time Delivery Percentage
- Delayed Orders
- Average Review Score

### Key Visuals
- On-Time vs Delayed Deliveries
- Orders by Delivery Status
- Customer Review Score by Delivery Performance

### Business Insights
- Delayed deliveries significantly reduce customer satisfaction
- Over 92% of deliveries arrive on time
- Delivery operations strongly influence customer reviews

---

## 4. Product Performance Analysis

This page focuses on category-level product performance.

### Key Metrics
- Total Product Categories
- Top Category Revenue
- Average Category Revenue

### Key Visuals
- Top Product Categories by Revenue
- Top Product Categories by Orders

### Business Insights
- A few product categories dominate marketplace revenue
- High-demand categories drive overall platform growth
- Revenue contribution is concentrated among top-performing categories

---

## 5. Seller Performance Analysis

This page evaluates marketplace seller contribution and seller distribution.

### Key Metrics
- Total Sellers
- Top Seller Revenue
- Average Seller Revenue

### Key Visuals
- Top Sellers by Revenue
- Seller Revenue Distribution by State

### Business Insights
- Marketplace revenue depends heavily on top-performing sellers
- Seller activity is concentrated in southeastern Brazil
- A small number of sellers contribute disproportionately to total revenue

---

# DAX Measures Used

Some important DAX measures created in this project include:

```DAX
Total Revenue =
SUM(order_payments[payment_value])
```

```DAX
Total Orders =
DISTINCTCOUNT(orders[order_id])
```

```DAX
Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)
```

```DAX
Repeat Customer Rate =
DIVIDE([Repeat Customers], [Unique Customers], 0)
```

```DAX
On-Time Delivery % =
DIVIDE([On-Time Orders], [Total Orders], 0)
```

```DAX
Top Seller Revenue =
MAXX(
    VALUES(sellers[seller_id]),
    CALCULATE(SUM(order_items[price]))
)
```

---

# Tools & Technologies

- Power BI
- DAX (Data Analysis Expressions)
- Power Query
- Data Modeling
- Interactive Visualizations

---

# Key Insights

- Revenue growth peaked between late 2017 and early 2018
- Customer retention is relatively low compared to one-time purchases
- Delivery delays have a direct negative impact on review scores
- Product revenue is concentrated among a few top categories
- Marketplace performance heavily depends on a small number of sellers

---

# Dashboard Screenshots

## Executive Overview
<img width="871" height="491" alt="image" src="https://github.com/user-attachments/assets/09831485-a253-4994-bdaf-5748ff9b4bfa" />


---

## Customer Analytics
<img width="876" height="486" alt="image" src="https://github.com/user-attachments/assets/1ba49c90-c386-453d-9927-335115a0e13c" />


---

## Delivery & Operations Analysis
<img width="874" height="486" alt="image" src="https://github.com/user-attachments/assets/20e5492e-d14c-435c-ae01-b3af839ad957" />


---

## Product Performance Analysis
<img width="876" height="485" alt="image" src="https://github.com/user-attachments/assets/f7a0027d-58c1-4d59-872e-49a92d34ffab" />


---

## Seller Performance Analysis
<img width="873" height="485" alt="image" src="https://github.com/user-attachments/assets/4a7ff0bd-9368-4bd9-8455-2c49c3f66534" />


---

# Challenges Faced

Some challenges encountered during the project included:

- Building proper table relationships
- Managing DAX filter context
- Handling geographic mapping issues in Power BI
- Cleaning category and location data
- Designing dashboards with proper visual hierarchy

---

# Future Improvements

Possible future improvements:
- Customer segmentation analysis
- Profit margin analysis
- Forecasting and predictive analytics
- Drill-through pages
- Advanced seller performance benchmarking
- Inventory optimization analysis

---

# Conclusion

This project demonstrates how Business Intelligence tools can transform raw e-commerce data into actionable insights.

The dashboard provides visibility into:
- Marketplace performance
- Customer behavior
- Delivery operations
- Product demand
- Seller contribution

The project also demonstrates practical skills in:
- Data modeling
- DAX calculations
- Dashboard design
- Business storytelling
- Analytical problem solving

---
