
# 🛍️ E-Commerce Customer Segmentation & Recommendation System

## 📌 Project Overview
This project focuses on **analyzing and segmenting e-commerce customers** based on their purchase behavior using **RFM (Recency, Frequency, Monetary) analysis** and **machine learning clustering**.  

The goal is to help businesses identify key customer segments, understand their value, and provide **personalized product recommendations** to enhance **retention and revenue growth**.  

By combining **Python-based analytics** with **Power BI visualization**, this project bridges the gap between **data insights** and **business decision-making**.

---

## 🎯 Objectives
- Identify distinct customer groups based on purchasing behavior.  
- Apply unsupervised learning (K-Means) for segmentation.  
- Recommend top products for each segment using transaction data.  
- Visualize insights in Power BI for strategic decisions.  

---

## 📂 Dataset Description
**Dataset Used:** [UCI Online Retail Dataset (2010–2011)](https://archive.ics.uci.edu/ml/datasets/online+retail)  

**Key Columns:**
| Column | Description |
|---------|--------------|
| `InvoiceNo` | Unique transaction ID |
| `StockCode` | Product code |
| `Description` | Product name |
| `Quantity` | Number of items purchased |
| `InvoiceDate` | Date of transaction |
| `UnitPrice` | Price per item |
| `CustomerID` | Unique customer identifier |
| `Country` | Customer location |

---

## 🧹 Step 1: Data Cleaning
Performed thorough data preprocessing:
- Removed missing `CustomerID` entries.  
- Filtered out negative/zero quantities (returns).  
- Created a **TotalPrice** column (`Quantity × UnitPrice`).  
- Parsed dates and ensured correct data types.  
- Exported clean dataset for analysis (`cleaned_ecommerce_data.csv`).  

---

## 🧮 Step 2: RFM Feature Engineering
Derived customer-level metrics:  

| Metric | Definition | Formula |
|---------|-------------|----------|
| **Recency** | Days since last purchase | `max_date - last_purchase_date` |
| **Frequency** | Total number of purchases | `count(InvoiceNo)` |
| **Monetary** | Total spending | `sum(TotalPrice)` |

The RFM table was standardized and saved as `rfm_metrics.csv`.

---

## 🤖 Step 3: Customer Segmentation (K-Means Clustering)
**Goal:** Group customers with similar purchasing behavior.  

**Process:**
1. Scaled RFM data using `StandardScaler`.  
2. Determined optimal number of clusters using the **Elbow Method** and **Silhouette Score**.  
3. Applied **K-Means** with optimal K (typically 4).  
4. Analyzed and labeled clusters:
   - 🟢 *Champions*: High frequency, high spenders  
   - 🔵 *Loyal Customers*: Regular buyers with moderate recency  
   - 🟡 *At Risk*: Used to buy frequently but inactive now  
   - 🔴 *Hibernating*: Low frequency, low monetary value  

Cluster results saved in `rfm_clusters.csv`.

---

## 🧠 Step 4: Product Recommendation Engine
To personalize engagement, the system:
1. Merged RFM clusters with product-level data.  
2. Identified **Top 5 products per cluster** by quantity purchased.  
3. Attached these as **recommendation lists** to each customer segment.  

Final dataset saved as `customer_recommendations.csv`.

---

## 📊 Step 5: Power BI Dashboard
Created an interactive Power BI dashboard to visualize:
- Customer distribution by segment  
- Average Recency, Frequency, Monetary by cluster  
- Revenue contribution by segment  
- Top products recommended for each customer group  

The dashboard enables business users to quickly interpret which segments need targeted marketing or retention strategies.

---

## 🧰 Tech Stack
| Category | Tools / Libraries |
|-----------|-------------------|
| **Programming** | Python |
| **Data Analysis** | Pandas, NumPy |
| **Machine Learning** | Scikit-learn (K-Means, StandardScaler) |
| **Visualization** | Matplotlib, Seaborn, Power BI |
| **File Handling** | CSV, Jupyter Notebook |

---

