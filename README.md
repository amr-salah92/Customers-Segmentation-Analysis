# Online Retail - Customer Segmentation Analysis using RFM and Clustering

---

## Table of Contents  
1. [Project Name](#project-name)  
2. [Project Background](#project-background)  
3. [Project Goals](#project-goals)  
4. [Insights and Recommendations](#insights-and-recommendations)  
   - [RFM Analysis](#rfm-analysis)  
   - [Customer Segmentation](#customer-segmentation)  
5. [Data Collection and Sources](#data-collection-and-sources)  
6. [Formal Data Governance](#formal-data-governance)  
7. [Regulatory Reporting](#regulatory-reporting)  
8. [Methodology](#methodology)  
9. [Data Structure & Initial Checks](#data-structure--initial-checks)  
10. [Documenting Issues](#documenting-issues)  
11. [Executive Summary](#executive-summary)  
12. [Insights Deep Dive](#insights-deep-dive)  
13. [Recommendations](#recommendations)  
14. [Future Work](#future-work)  
15. [Technical Details](#technical-details)  
16. [Assumptions and Caveats](#assumptions-and-caveats)  

---

## Project Name  
**Online Retail - Customer Segmentation Analysis using RFM and Clustering**  

---

## Project Background  
The dataset belongs to a **UK-based online retailer** operating between **01/12/2010 to 09/12/2011**, selling unique gift items across Europe. The company operates on a B2C model, fulfilling orders via online transactions.  

**Key Dataset Stats**:  
- **540,000+ records** with **37,000+ customers**.  
- **80% of transactions** originate from the UK.  
- Columns: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.  


---

## Project Goals  
1. **Understand Customer Behavior**: Analyze purchasing frequency, recency, and monetary value.  
2. **Segment Customers**: Identify high-value, loyal, and at-risk customers for targeted marketing.  
3. **Drive Data-Driven Decisions**: Optimize stock management and marketing strategies.  

---

## Insights and Recommendations  

### RFM Analysis  
1. **Recency**:  
   - Top 25% of customers made purchases within the last 30 days.  
2. **Frequency**:  
   - Top 10% of customers accounted for **30% of repeat transactions**.  
3. **Monetary**:  
   - Top spenders contributed **over £10,000 each** (disproportionate revenue share).  

### Customer Segmentation (K-Means Clustering)  
| Cluster | Profile                          | Strategy                               |  
|---------|----------------------------------|----------------------------------------|  
| 0       | **Inactive, Low-Value**          | Reactivation campaigns                 |  
| 1       | **High Frequency, Low Spend**    | Upsell/cross-sell bundles              |  
| 2       | **Premium, Loyal**               | VIP loyalty programs                   |  
| 3       | **Recent, Low Engagement**       | Welcome offers to boost retention      |  



![output](https://github.com/user-attachments/assets/78dbc406-e7b8-426f-b96c-2d99f56eb8fa)


---

## Data Collection and Sources  
- **Source**: Internal ERP database (`online_retail.xlsx`, Sheet 0).  
- **Scope**: Transactions from **2010–2011**, excluding external APIs.  

---

## Formal Data Governance  
1. **Missing Values**:  
   - **25% missing `CustomerID`**: Rows excluded to focus on identifiable customers.  
2. **Data Validity**:  
   - Filtered out **negative quantities** (returns) and **zero/negative prices**.  

---

## Regulatory Reporting  
- **GDPR Compliance**: `CustomerID` anonymized; no PII used.  
- **Financial Compliance**: Returns (negative quantities) excluded from revenue calculations.  

---

## Methodology  
1. **Data Cleaning**:  
   - Removed invalid entries (e.g., missing `CustomerID`, negative values).  
2. **RFM Scoring**:  
   - **Recency**: Days since last purchase.  
   - **Frequency**: Total transactions per customer.  
   - **Monetary**: Total spend per customer.  
3. **Clustering**:  
   - Standardized RFM scores using `StandardScaler`.  
   - Applied **K-Means (k=4)** validated by silhouette analysis.  

---

## Data Structure & Initial Checks  
**Main Table**: `df` (540k rows × 8 columns)  

| Column         | Description                           | Key Insights                          |  
|----------------|---------------------------------------|---------------------------------------|  
| `InvoiceNo`    | Transaction identifier                | 28k unique invoices                   |  
| `CustomerID`   | Anonymized customer identifier        | 37k unique customers (25% missing)    |  
| `Quantity`     | Units sold                            | Filtered to positive values only      |  
| `UnitPrice`    | Price per unit                        | Removed zero/negative entries         |  


![1732803067118](https://github.com/user-attachments/assets/07b6cc0b-e5b6-42d9-89e3-0f8bfe7a9e39)

---

## Documenting Issues  
| Table | Column      | Issue                      | Magnitude | Solvable | Resolution                     |  
|-------|-------------|----------------------------|-----------|----------|--------------------------------|  
| `df`  | `CustomerID`| 25% missing                | High      | Yes      | Excluded rows                  |  
| `df`  | `Quantity`  | Negative values (returns)  | Medium    | Yes      | Filtered out                   |  
| `df`  | `UnitPrice` | Zero/negative prices       | Low       | Yes      | Removed invalid entries        |  

---

## Executive Summary *(For a Marketing Manager)*  
1. **Top 10% of Customers** drive **50% of revenue** — prioritize retention.  
2. **40% of Customers** are inactive — launch reactivation campaigns.  
3. **Germany** shows untapped potential with higher average order value.  



---

## Insights Deep Dive  

### RFM Analysis  
- **Recency**: 75% of customers purchased within the last 90 days.  
- **Frequency**: 60% of customers made only **1 transaction**.  
- **Monetary**: Top 5% spenders generated **£500,000+** in revenue.  

### Customer Segmentation  
- **Cluster 2 (Premium)**:  
  - 15% of customers, 60% of revenue.  
  - Average spend: **£1,200/year**.  
- **Cluster 0 (Inactive)**:  
  - 40% of customers, 5% of revenue.  
  - Last purchase: **>180 days ago**.  

---

## Recommendations  

| Observation                                  | Recommendation                                  |  
|---------------------------------------------|------------------------------------------------|  
| Cluster 2 drives 60% of revenue             | Introduce tiered loyalty rewards               |  
| Cluster 0 has low engagement                | Send personalized reactivation offers          |  
| High AOV in Germany                         | Localize marketing campaigns for DE/NL markets |  
| Frequent returns on specific products       | Audit product quality and descriptions         |  

---

## Future Work  
1. **Product-Category Analysis**: Link `StockCode` to categories for deeper insights.  
2. **Time-Series Forecasting**: Predict customer lifetime value (LTV).  
3. **Behavioral Data Integration**: Add web analytics (e.g., cart abandonment).  

---

## Technical Details  
**Tools**:  
- **Python**: Pandas (cleaning), Scikit-learn (K-Means), Matplotlib/Seaborn (visualization).
  
[code](https://github.com/amr-salah92/Customers-Segmentation-Analysis/blob/main/online%20retail.ipynb)



---

## Assumptions and Caveats  
1. **Missing `CustomerID`**: Assumed to be guest checkouts (excluded).  
2. **Partial December 2011 Data**: Seasonal trends may be underrepresented.  
3. **Country Data**: No standardization applied (e.g., "UK" vs. "United Kingdom").  

