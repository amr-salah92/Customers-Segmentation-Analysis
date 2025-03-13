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

![1732803067129](https://github.com/user-attachments/assets/de9b4856-9892-47a8-b246-6150ae999804)


## Insights Deep Dive

### Top Products
Most purchased items were small, low-cost gifts, indicating a gifting-oriented business model.

### Seasonality
Sales spiked in **November and December**, aligning with holiday shopping trends.
![1732804207628](https://github.com/user-attachments/assets/d2c6fdbf-0aef-44e9-a2b4-514c7e45aec6)
### Customer Segmentation
- **20%** of customers accounted for over **80%** of total sales.
- Emphasized the importance of loyalty programs for high-value customers.
![1732803755513](https://github.com/user-attachments/assets/65bfde58-05d0-4f57-b737-ad14b28583b7)

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
