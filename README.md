# 🛒 E-Commerce Data Analysis Project

A complete end-to-end data analytics project using **Python**, **PostgreSQL**, and **Power BI** — covering data ingestion, cleaning, SQL-based analysis, and interactive dashboards.

---

## 🎯 Business Problem

The company operates across multiple countries and stores, selling products across several categories and brands. Leadership needs data-driven answers to:

- Which countries, stores, and product categories drive the most **revenue and profit** — and which underperform?
- Which **customer segments** are most valuable, and which are at risk of churn?
- Are there **operational issues** (e.g., missing delivery dates, low store efficiency) affecting customer experience or profitability?
- What **seasonal or growth trends** should inform inventory and marketing planning?

This project analyzes transactional, product, customer, and store data to answer these questions and turn them into actionable recommendations for sales, marketing, and operations teams.

---

## 📁 Project Structure

```
e-commerce-analysis/
├── E_commerce_project.ipynb      # Jupyter Notebook (ETL + SQL Analysis)
├── E-commerce_data_analysis.pbix # Power BI Dashboard
├── dataset/
│   ├── Customers_fixed.csv
│   ├── Exchange_Rates.csv
│   ├── Products.csv
│   ├── Saless.csv
│   └── Storess.csv
└── README.md
```

---

## 📊 Dataset Overview

| Table           | Description                                      |
|-----------------|--------------------------------------------------|
| `customers`     | Customer demographics (name, country, birthday, gender) |
| `products`      | Product details (name, brand, category, cost, price) |
| `sales`         | Order transactions (order number, quantity, dates) |
| `stores`        | Store information (location, size in sq meters) |
| `exchange_rates`| Currency exchange rate data                      |

---

## 🔧 Tech Stack

| Tool | Purpose |
|------|---------|
| **Python (pandas, SQLAlchemy)** | Data loading & cleaning |
| **PostgreSQL** | Relational database & SQL queries |
| **Jupyter Notebook** | EDA & analysis workflow |
| **Power BI** | Interactive visualizations |

---

## ⚙️ Setup & Installation

### 1. Clone the Repository
```bash
git clone https://github.com/nazmul23423/SQL-Python-PowerBI-Ecommerce-Analysis.git
cd SQL-Python-PowerBI-Ecommerce-Analysis
```

### 2. Install Python Dependencies
```bash
pip install pandas sqlalchemy psycopg2-binary
```

### 3. Configure PostgreSQL
Create the database and update the connection string in the notebook:
```python
engine = create_engine("postgresql://your_user:your_password@localhost:5432/E_commerce_database")
```

### 4. Place CSV Files
Put all CSV files inside the `dataset/` folder and update `folder_path` in the notebook.

### 5. Run the Notebook
```bash
jupyter notebook E_commerce_project.ipynb
```

---

## 🧹 Data Pipeline

### Step 1 — Load CSVs to PostgreSQL
- Reads 5 CSV files and auto-detects column data types
- Sanitizes column names (removes spaces, dashes, dots)
- Uploads all tables to PostgreSQL using `to_sql()`

### Step 2 — Data Quality Check
- Checks shape, missing values, and duplicate rows for each table

### Step 3 — Data Cleaning
- Converts `Unit_Cost_USD` and `Unit_Price_USD` from string (with `$` and `,`) to numeric
- Parses `Order_Date` and `Delivery_Date` as datetime
- Removes or handles null values in the `stores` table

---

## 🔍 SQL Analysis — Business Questions Answered

- **Q1** — Total Orders and Revenue per Country
- **Q2** — Product Category-wise Total Units Sold
- **Q3** — Top 10 Best-Selling Products
- **Q4** — Count of NULL Delivery Dates per Store
- **Q5** — Brand-wise Revenue and Profit Margin
- **Q6** — Monthly Sales Trend
- **Q7** — Store Revenue per Square Meter
- **Q8** — Sales by Age Group and Gender
- **Q9** — Top 3 Products per Category by Profit
- **Q10** — Total Revenue by Country and Product
- **Q11** — Customers Who Shopped from Multiple Countries' Stores
- **Q12** — Monthly Running Total & Month-over-Month Growth %
- **Q13** — RFM Customer Segmentation (Recency, Frequency, Monetary)
- **Q14** — Year-over-Year Quarterly Revenue Pivot
- **Q15** — Top 5 Revenue Generating Brands

📓 Full queries and outputs: [Jupyter Notebook](https://github.com/nazmul23423/SQL-Python-PowerBI-Ecommerce-Analysis/blob/master/E_commerce_project.ipynb)

---

## 📈 Power BI Dashboard

The `.pbix` file includes interactive visuals covering:
- Revenue by country and category
- Monthly & quarterly sales trends
- Brand and product performance
- Customer demographic analysis
- Store performance metrics

> Open the `.pbix` file using **Power BI Desktop** (free download from Microsoft).

🖼️ Preview: [Dashboard image](https://github.com/nazmul23423/SQL-Python-PowerBI-Ecommerce-Analysis/blob/master/Powerbi_dashboard_image.png)

---

## 💡 Key Insights

### 📈 1. Strong Overall Business Performance
- The business generated approximately **$11.07M** in total sales and **$6.51M** in total profit from nearly **11.9K orders**, selling around **37K products**.
- The strong profit level indicates healthy profitability and effective pricing strategies.

---

### 💻 2. Product Category Performance
- **Computers** is the most profitable category, contributing approximately **$2.12M** in profit.
- **Home Appliances** ranks second with around **$1.48M** in profit.
- Categories such as **Games & Toys**, **Audio**, and **Music, Movies & Audio Books** generate comparatively lower profits, highlighting opportunities for product optimization and targeted marketing.

---

### 📅 3. Monthly Order Trend
- Monthly order volume remains relatively stable throughout the year.
- **February** recorded the highest order volume with approximately **1.6K orders**.
- Order volume declined noticeably during **March** and **April**, suggesting possible seasonal demand fluctuations.

---

### 🌍 4. Geographic Sales Distribution
- The **United States** is the strongest market, contributing approximately **18K units sold**, significantly outperforming all other countries.
- The **United Kingdom** and **Germany** are the next highest-performing markets.
- **France** and **Italy** record comparatively lower sales volumes, indicating potential growth opportunities.

---

### 👥 5. Customer Gender Analysis
- Sales are almost evenly distributed between male and female customers.
- **Female customers account for approximately 51.86% of total sales**, while **male customers contribute 48.14%**, reflecting balanced customer engagement.

---

### 🏷️ 6. Brand Performance
- **Adventure Works** is the top-performing brand, generating approximately **$2.4M** in sales.
- Sales decline gradually across the remaining brands, with **Tailspin Toys** recording the lowest sales.
- Revenue is concentrated among a few leading brands, suggesting potential for expanding the performance of lower-selling brands.

---

### 🎨 7. Product Color Preference
- **Silver** products generate the highest revenue (approximately **$21.2K**).
- **White** products rank second in sales performance.
- **Blue** products record the lowest revenue, indicating comparatively weaker customer demand.

---

## ✅ Recommendations

### 🚀 1. Focus on High-Profit Categories
Increase inventory investment and marketing efforts for **Computers** and **Home Appliances**, as these categories generate the highest profit and offer the greatest return on investment.

---

### 📉 2. Improve Underperforming Categories
Review pricing strategies, product assortment, and promotional campaigns for low-performing categories such as **Games & Toys**, **Audio**, and **Music, Movies & Audio Books** to improve profitability.

---

### 🌍 3. Expand High-Performing Markets
Prioritize marketing campaigns, inventory allocation, and customer retention initiatives in the **United States**, **United Kingdom**, and **Germany**, where sales performance is strongest.

---

### 📍 4. Increase Sales in Low-Performing Countries
Develop localized marketing strategies, promotional offers, and product selections for markets such as **France** and **Italy** to improve customer engagement and sales growth.

---

### 📅 5. Prepare for Seasonal Demand
Since order volume declines during **March** and **April**, introduce seasonal promotions, targeted advertising, and inventory planning to maintain consistent sales throughout the year.

---

### 🏷️ 6. Strengthen Brand Performance
Continue investing in top-performing brands such as **Adventure Works**, while evaluating pricing, product positioning, and promotional strategies for lower-performing brands like **Tailspin Toys**.

---

### 🎨 7. Optimize Product Inventory
Maintain higher inventory levels for popular product colors such as **Silver** and **White**, while reviewing demand forecasting for lower-selling colors like **Blue** to reduce excess inventory.

---

### 👥 8. Enhance Customer Engagement
Although sales are balanced across genders, implement personalized marketing campaigns and loyalty programs based on customer purchasing behavior to improve retention and lifetime value.

---

## 🗃️ Database Schema (ERD Overview)

```
customers ──< sales >── products
               │
            stores
```

- `sales.CustomerKey` → `customers.CustomerKey`
- `sales.ProductKey`  → `products.ProductKey`
- `sales.StoreKey`    → `stores.StoreKey`

---

## 📝 Author

**Md Nazmul Islam**
- GitHub: [@nazmul23423](https://github.com/nazmul23423)
- LinkedIn: [md-nazmul-islam-8b5770388](https://linkedin.com/in/md-nazmul-islam-8b5770388)
