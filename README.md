# 📊 Sales Data Analysis (Python, Pandas, NumPy, Seaborn)

A beginner-friendly **data analysis project** using Python libraries — **Pandas**, **NumPy**, **Matplotlib**, and **Seaborn** — to explore, clean, and visualize sales data.

## 🚀 Overview
Analyze a CSV file containing sales records (OrderID, Date, Region, Product, Quantity, UnitPrice, Discount).  
Tasks include data cleaning, total sales computation, outlier detection, and visualizing regional & monthly sales trends.

## 🧰 Tools & Libraries
- Python 🐍  
- Pandas & NumPy — data manipulation  
- Matplotlib & Seaborn — visualization  

Install dependencies:
```bash
pip install -r requirements.txt
```

## 📂 Key Steps
```python
import pandas as pd, numpy as np, seaborn as sns, matplotlib.pyplot as plt

df = pd.read_csv('sales_data.csv')
df['TotalSales'] = df['Quantity'] * df['UnitPrice'] * (1 - df['Discount'])
region_sales = df.groupby('Region')['TotalSales'].sum()
monthly_sales = df.groupby(pd.to_datetime(df['Date']).dt.to_period('M'))['TotalSales'].sum()
sns.barplot(x=region_sales.index, y=region_sales.values)
plt.title("Total Sales by Region")
plt.show()
```

## 📈 Insights
- Western region has the highest total sales  
- Laptops and Phones dominate product sales  
- Some high-value orders act as outliers  
- Seasonal trends visible in monthly sales

## 🧑‍💻 Author
**Ishwar** — Aspiring Data Analyst | Python • SQL • Power BI
