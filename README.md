# 🛒 Instacart Market Basket & Customer Analytics  
*An End-to-End SQL & Python Case Study*  

---

## 1. Project Introduction 🎯

This repository delivers a complete analytics case study on Instacart’s e-commerce order data, covering product, customer, and behavioral analytics from end to end.  
**All data cleaning steps are fully documented in the included Jupyter notebook, so you can follow every stage of the data preparation process.**

---

## 2. Dataset & Data Pipeline

- **Source:** [Instacart Market Basket Analysis | Kaggle](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysis?resource=download)  
- **Raw Data:** ~3 million orders, 200K+ users, 50K+ products, 20 departments, 130 aisles
- **Files:** `orders.csv`, `order_products__prior.csv`, `order_products__train.csv`, `products.csv`, `departments.csv`, `aisles.csv`
- **Data Cleaning:**  
  - See all cleaning stages in [`Instacart Market Basket Data Cleaning.ipynb`](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb)
  - Inspected and cleaned missing values, anomalies, datatypes, and duplicates
  - Exported cleaned tables as CSV for SQL analytics

---

## 3. Tools & Technologies 🛠️

- **Python (Jupyter Notebook):**  
  - Data exploration & cleaning  
  - Data cleaning notebook: [`Instacart Market Basket Data Cleaning.ipynb`](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb)
- **SQL Server Management Studio (SSMS):**  
  - Data loading & advanced SQL analysis
- **Visualization:**  
  - SQL output screenshots

---

## 4. Data Preparation Workflow 📦

1. **Data Cleaning in Jupyter Notebook**
   - All data quality checks, filtering, and exporting are detailed step-by-step in the notebook
   - [Open the notebook here](./Instacart%20Market%20Basket%20Data%20Cleaning%20(1).ipynb) to follow each cleaning stage

2. **Database Loading in SQL**
   - Created database & loaded cleaned CSVs into SSMS
   - Checked relationships and validated schema
  
## 5. Analysis Workflow 🧭

The following sections mirror the analytic flow from raw data to business insight:

1. **Top Products Sold**  
2. **Department & Aisle Performance**  
3. **Order Volume Patterns (Day / Hour)**  
4. **Product Reorder Rate**  
5. **Customer Frequency Segmentation**  
6. **Basket Size & CLV Proxy**  
7. **Product Affinity Analysis (Pairs/Trios)**  
8. **Churn Risk Analysis**  
9. **Cohort Retention Analysis**

Each section includes:
- Business question  
- SQL screenshot & sample output  
- Insight & recommendation

  ## 6.Top Products Sold
**Business Question:** Which products sell most frequently?
![image](https://github.com/user-attachments/assets/e82076e9-0b67-4a78-b1c0-6fa63296e0a0) ![image](https://github.com/user-attachments/assets/66dd566d-d865-4d8e-b948-125005658777)

In this analysis, I identified the top 10 best-selling products by joining the orders data with product details and counting how many times each product appeared in customer carts. The results show that bananas, both regular and organic, dominate sales, followed closely by other fresh fruits like strawberries and avocados. Organic products are especially popular among shoppers, making up most of the top sellers. This pattern highlights a strong customer preference for fresh and organic produce, suggesting these categories are key drivers of revenue and should be prioritized in inventory and marketing strategies.

## 7.Category/Department Analysis
**Business Question:** Which departments and aisles generate the highest sales volume? Are there any standout categories that outperform the rest?
![image](https://github.com/user-attachments/assets/74609144-00ad-46f2-b946-9fa0da244cb7) ![image](https://github.com/user-attachments/assets/203da987-c7a5-4416-8049-4065fd2363ea)

Looking at the department sales breakdown, it's clear that "dairy eggs" is the leading category by a wide margin, with nearly twice as many sales as the next department, "snacks." Other high-performing categories include "beverages," "frozen," and "pantry," all showing strong consumer demand. Meanwhile, departments like "alcohol," "pets," "other," and especially "bulk" make up only a small fraction of total sales, suggesting either a lower product variety or less frequent purchases in those areas. Overall, the data reflects typical grocery shopping patterns, with core staples like dairy, snacks, and beverages dominating the basket.

## 8.  Best-Selling Aisles: Sales Distribution by Aisle
**Business Question:** Which aisles drive the most sales across the entire store, and how is customer demand distributed among different product aisles?
**Business Rationale:** Understanding sales performance at the aisle level helps uncover shopping patterns that may not be visible at the department level. This insight supports more targeted product placement, merchandising decisions, and tailored marketing campaigns, ultimately driving revenue growth.










