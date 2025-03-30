# Online Retail Customer Segmentation (K-means Clustering, RFM analysis)

## Project Overview
This project simulates a real-world customer segmentation analysis for **Regal Gifts Ltd.**, similar to work done at Kantar. Using historical transaction data, we segment customers based on purchasing behavior to improve targeting strategies, optimize discounts, and boost customer retention. The project involves data cleaning, feature engineering, exploratory analysis, and clustering using K-Means and RFM analysis to uncover actionable insights.

## Download Dataset: https://archive.ics.uci.edu/dataset/502/online+retail+ii

## Dataset Information
The dataset contains transactions from a UK-based online retailer between **December 1, 2009, and December 9, 2011**. The company primarily sells unique all-occasion giftware, with many customers being wholesalers.

### Key Columns:
- **InvoiceNo**: Unique identifier for each transaction (Cancellation if it starts with 'C').
- **StockCode**: Unique product code.
- **Description**: Product name.
- **Quantity**: Number of units purchased.
- **InvoiceDate**: Date and time of purchase.
- **UnitPrice**: Price per unit in pounds (£).
- **CustomerID**: Unique identifier for customers.
- **Country**: Customer’s country.

## Data Processing
### Steps Taken:
1. **Data Cleaning**: Removed null values, handled invalid InvoiceNo, Stockcodes, and filtered out anomalies.
2. **Feature Engineering**: Created three key features for customer segmentation:
   - **Monetary**: Total amount spent per customer.
   - **Frequency**: Number of purchases per customer.
   - **Recency**: Days since the last purchase.
3. **Outlier Handling**: Separated outliers and non-outliers data of Monetary, Frequecny and Recency for better analysis.
4. **Clustering with KMeans**: Segmented customers into meaningful groups.

## Customer Segmentation Insights
### Non-Outlier Clusters

| Cluster | Description  | Strategy |
|---------|-------------|----------|
| **0 (Yellow) - "Re-Engage"** | Low-value, infrequent buyers | Targeted marketing campaigns and special discounts |
| **1 (Green) - "Retain"** | High-value, frequent buyers (but not recent) | Loyalty programs and personalized offers |
| **2 (Blue) - "Nurture"** | Low-value, recent buyers | Relationship-building, excellent service, and incentives |
| **3 (Red) - "Reward"** | High-value, active buyers | VIP rewards and exclusive offers |

### Outlier Clusters

| Cluster | Description | Strategy |
|---------|-------------|----------|
| **-1 (Monetary Outliers) - "Pamper"** | High spenders but not frequent buyers | Personalized luxury offers |
| **-2 (Frequency Outliers) - "Upsell"** | Frequent buyers with lower spending | Bundle deals and upselling strategies |
| **-3 (Monetary & Frequency Outliers) - "Delight"** | Top-tier customers with extreme spending & frequency | VIP programs and exclusive incentives |

## Tools & Libraries Used
- **Python**
- **Pandas** (Data processing)
- **Matplotlib & Seaborn** (Data visualization)
- **StandardScaler** (Feature scaling)
- **KMeans Clustering** (Customer segmentation)

## How to Use
1. Clone the repository.
2. Install required libraries using:
   ```bash
   pip install pandas matplotlib seaborn scikit-learn
