# Online Retail Customers Segmentation Analysis

## Project Background & Overview
The **Online Retail II** dataset, sourced from the UCI Machine Learning Repository, contains transactional data for a United Kingdom-based online retailer from 2009 to 2010. It includes over 500,000 records, detailing invoices, stock codes, product descriptions, customer identifiers, and sales data.

The dataset serves as an excellent case study for analyzing e-commerce behavior and identifying sales trends.

## Project Goals
- **Understand Sales Dynamics**: Explore seasonal trends and peak shopping periods.
- **Customer Segmentation**: Classify customers based on their purchasing behaviors to identify high-value segments (using the clustering KNN algorithm).
- **Product Performance**: Evaluate product popularity and revenue contribution.

## Executive Summary
This analysis provided a comprehensive understanding of sales dynamics and customer behavior. Key highlights include:
- Identification of top-selling products.
- Insights into seasonal peaks around holidays such as Christmas.
- Customer segmentation revealed that a small percentage of customers contributed significantly to revenue.

---
# Data Structure and Overview

The dataset comprises the following key variables:

- **InvoiceNo**: Unique identifier for each transaction.
- **StockCode**: Unique identifier for each product.
- **Description**: Product description.
- **Quantity**: Number of products sold per transaction.
- **InvoiceDate**: Date and time of the transaction.
- **UnitPrice**: Price of the product per unit in GBP.
- **CustomerID**: Unique identifier for each customer.
- **Country**: Customer location.
![1732803067118](https://github.com/user-attachments/assets/07b6cc0b-e5b6-42d9-89e3-0f8bfe7a9e39)


## Insights Deep Dive

### Top Products
Most purchased items were small, low-cost gifts, indicating a gifting-oriented business model.

### Seasonality
Sales spiked in **November and December**, aligning with holiday shopping trends.

### Customer Segmentation
- **20%** of customers accounted for over **80%** of total sales.
- Emphasized the importance of loyalty programs for high-value customers.

![output](https://github.com/user-attachments/assets/78dbc406-e7b8-426f-b96c-2d99f56eb8fa)

### Geographic Distribution
- The majority of revenue was generated in the **UK**.
- International customers had a **higher average order value**.

### Inventory Management
- Some products with high quantities sold were frequently **returned**, highlighting potential quality issues or mismatched customer expectations.

---

## Recommendations

1. **Focus on High-Value Customers**
   - Implement targeted marketing campaigns and loyalty programs to retain and engage top customers.
2. **Optimize Inventory**
   - Improve inventory forecasting by aligning stock with seasonal demand.
