# 🛒 E-Commerce Data Analysis Project

A complete end-to-end data analytics project using **Python**, **PostgreSQL**, and **Power BI** — covering data ingestion, cleaning, SQL-based analysis, and interactive dashboards.

---

## 📁 Project Structure

```
e-commerce-analysis/
├── E_commerce_project.ipynb     # Jupyter Notebook (ETL + SQL Analysis)
├── E-commerce_data_analysis.pbix # Power BI Dashboard
├── data/
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

- **Tool**         — **Purpose**                          

- **Python (pandas, SQLAlchemy)**   — Data loading & cleaning 
- **PostgreSQL** — Relational database & SQL queries 
- **Jupyter Notebook**  — EDA & analysis workflow     
- **Power BI** — Interactive visualizations        

---

## ⚙️ Setup & Installation

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ecommerce-analysis.git
cd ecommerce-analysis
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
Put all CSV files inside the `data/` folder and update `folder_path` in the notebook.

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

## Question 

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

---

## 📈 Power BI Dashboard

The `.pbix` file includes interactive visuals covering:
- Revenue by country and category
- Monthly & quarterly sales trends
- Brand and product performance
- Customer demographic analysis
- Store performance metrics

> Open the `.pbix` file using **Power BI Desktop** (free download from Microsoft).

---

## 💡 Key Insights

- **Geographic Revenue** — Identifies which countries generate the highest sales volume and revenue
- **Brand Profitability** — Compares revenue vs. profit margin across brands
- **Customer Segmentation** — RFM model helps identify high-value, at-risk, and new customers
- **Seasonal Trends** — Monthly and quarterly analysis reveals peak sales periods
- **Delivery Issues** — Stores with high NULL delivery dates flagged for operational review

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

**Your Name**
- GitHub: [ @nazmul23423](https://github.com/your-username)
- LinkedIn: [ md-nazmul-islam-8b5770388](https://linkedin.com/in/md-nazmul-islam-8b5770388)
