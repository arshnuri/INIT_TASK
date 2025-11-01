# E-Commerce Data Analysis Notebook

## Author
**Name:** Mohammed Arsh Nuri 

---

## Summary / Approach
This project performs end-to-end retail data analysis by integrating data from transactions, customers, and product catalogs.
The workflow focuses on data cleaning, feature engineering, customer-level insights, and monthly performance metrics using fully vectorized operations for efficiency.

### Core Steps:

#### 1. Data Loading & Inspection
- Loaded and inspected `transactions.csv`, `customers.csv`, and `products.csv`.
- Checked for missing values and data inconsistencies.
- Verified column data types and dataset dimensions.

#### 2. Data Cleaning & Preprocessing
- Handled missing numeric values using the **median** and categorical values using the **mode**.
- Converted `timestamp` column to datetime format and extracted features like `hour_of_day`, `weekday`, and `month_num`.
- Identified and handled duplicate transaction IDs.

#### 3. Feature Engineering
- Calculated derived metrics: `revenue_amt = quantity × price` and `profit_margin`.
- Created time-based features such as `month_period` for monthly aggregations.
- Extracted `email_domain` from customer email addresses for duplicate detection.

#### 4. Data Integration
- Merged all datasets (transactions, customers, products) into a unified `final_df` / `combined_df` frame.
- Performed left joins to preserve all transaction records while enriching with customer and product details.

#### 5. Customer Metrics
- Computed **total revenue**, **number of transactions**, **average order value**, and **most frequent purchase category** per customer.
- Generated customer summary reports sorted by revenue contribution.

#### 6. Monthly Metrics
- Aggregated key metrics by month, including:
  - Total revenue
  - Active customer count
  - Total orders
  - Average order value
  - **Revenue growth percentage** (month-over-month)

#### 7. Product Performance Analysis
- Identified top 10 products by:
  - Total revenue
  - Quantity sold
  - Average profit margin
- Analyzed product performance across different categories.

#### 8. RFM Segmentation
- Implemented **Recency, Frequency, Monetary** analysis to classify customers into segments:
  - **Loyal**: High engagement across all metrics
  - **Active**: Moderate engagement
  - **At Risk**: Low engagement, needs retention efforts
- Created RFM scores and tags for targeted marketing campaigns.

#### 9. Fraud & Anomaly Detection
- Detected irregular transactions based on:
  - Unusual high-quantity low-price patterns
  - Multiple rapid purchases within 1 hour
- Flagged suspicious transactions with detailed reasons for further investigation.

#### 10. Time-Series Analysis
- Calculated **7-day moving average** for daily revenue to smooth out fluctuations.
- Analyzed daily sales trends and patterns.

#### 11. Customer Behavior Profiling
- Computed:
  - Days to first purchase after signup
  - Average purchase gap (time between consecutive orders)
  - Category variety (number of unique product categories purchased)
  - Most frequently used payment method
- Identified customer lifecycle patterns.

#### 12. Performance Optimization
- Demonstrated vectorized operations vs. iterative loops for filtering customers by age and country.
- Showcased significant performance improvements using pandas vectorization.

#### 13. Customer Lifetime Value (CLV)
- Calculated discounted lifetime value using monthly discount factor (default: 10%).
- Estimated long-term revenue contribution per customer with time-decay modeling.

#### 14. Duplicate Detection (Advanced Task)
- Identified potential duplicate customers based on:
  - **Fuzzy name matching** using RapidFuzz (token_sort_ratio > 85%)
  - **Email domain similarity**
  - **Transaction overlap** (purchased same products within 7 days)
- Assigned confidence scores combining all three signals for prioritized review.

---

## ⚙️ Dependencies / Libraries Used

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation, aggregation, and time-series operations |
| `numpy` | Mathematical operations and vectorization |
| `rapidfuzz` | String similarity matching for duplicate detection |
| `time` | Benchmarking performance of vectorized vs loop operations |
| `datetime` | Timestamp handling and date arithmetic (via pandas) |






