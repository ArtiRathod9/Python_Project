# 📊 Python Analysis and Code – Financial Dataset Summary

This analysis is based on a dataset containing financial data of products across different countries and segments. The goal is to derive business insights and visualize performance trends using Python.

---

## 1. 📦 Import Libraries and Load Data

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

file_xls = 'Financial Sample.xlsx'
data = pd.read_excel(file_xls)
```

- Libraries used: `pandas`, `matplotlib`, and `seaborn`
- The dataset is loaded and previewed using `.describe()` to understand its structure.

---

## 2. 💰 Segment Profitability Analysis

**Question**: Which segment generated the highest total profit?

```python
profit_by_segment = data.groupby('Segment')['Profit'].sum()
profit_by_segment.plot(kind='bar', title='Total Profit by Segment')
```

- A bar chart shows the total profit by segment.
- Insight: The visualization clearly identifies the most profitable segment.

---

## 3. 📈 Sales Trend Over Months

```python
monthly_sale = data.groupby('Month Name')['Gross Sales'].sum()
month_order = ['January', 'February', 'March', 'April', 'May', 'June', 
               'July', 'August', 'September', 'October', 'November', 'December']
monthly_sales = monthly_sale.reindex(month_order)
monthly_sales.plot(kind='line', title='Sales Trend Over Months')
```

- A line chart visualizes monthly sales trends.
- Insight: Seasonal patterns and monthly variations are clearly highlighted.

- 📈 Visualization Summary: Sales Trend Over Months
- This line chart titled "Sales Trend Over Months" displays the total sales across each month of the year.
![stov](stov.png)


# 🔍 Key Observations:
-January to August: Sales remained relatively steady with minor fluctuations, staying below 10 million.
- September: There was a sharp increase, indicating a strong surge in sales.
- October: Sales peaked dramatically, reaching the highest point, over 22.5 million.
- November: There was a drop, but sales remained significantly higher than most earlier months.
- December (if missing): Either not available or excluded from the dataset.

# 📊 Insights:
- The significant growth from August to October could indicate:
- A seasonal demand (e.g., holidays, back-to-school, or promotional events).
- A successful marketing campaign or product launch.
- Monitoring and planning around the September–October period could optimize business strategy
---

## 4. 🌍 Top Performing Country by Units Sold

**Question**: Which country sold the most units overall?

```python
units_by_country = data.groupby('Country')['Units Sold'].sum()
units_by_country.plot(kind='bar', title='Units Sold by Country')
```

- Bar chart reveals the country with the highest sales volume.
- Insight: Enables targeted regional strategies.

---

## 5. 🛍️ Compare Sales Across Products

**Question**: How do sales compare across different products?

```python
sales_by_product = data.groupby('Product')['Gross Sales'].sum()
sales_by_product.plot(kind='bar', title='Sales by Product')
```

- Visualization compares total sales per product.
- Insight: Identifies top and underperforming products.

---

## 6. 🎁 Explore Discount Distribution

**Question**: What is the distribution of discounts provided?

```python
plt.hist(data['Discounts'], bins=10, color='skyblue', edgecolor='black')
plt.title('Discount Distribution')
plt.xlabel('Discounts')
plt.ylabel('Frequency')
plt.show()
```

- Histogram highlights frequency and range of applied discounts.
- Insight: Most transactions received minimal or no discounts, suggesting potential for pricing strategy.

---

## 💡 Recommandation for Business

Based on insights:
- Focus on expanding in the **top-performing country**.
- Promote **best-selling products** more aggressively.
- Consider offering discounts strategically to boost underperforming areas.

