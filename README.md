# **Amazon Sales Analysis 📺**  

### 🚀 **Technologies Used:** Python | Jupyter Notebook | Pandas | NumPy  | Matplotlib |Seaborn.

### **🔍 Overview**  
This project analyzes **Amazon Sales** and viewing patterns to predict future content consumption trends. Using **Python** and libraries like **Pandas** and **NumPy**

### **📂 Dataset**  
- `Order ID` – Unique order identifier  
- `Date` – Order date  
- `Status` – Order status (Shipped, Cancelled, etc.)  
- `Fulfilment` – Fulfilment type (Amazon / Merchant)  
- `Sales Channel` – Platform where the sale happened  
- `Category` – Product category  
- `Size` – Product size  
- `Courier Status` – Shipping status  
- `Qty` – Quantity of products  
- `Currency` – Currency type  
- `Amount` – Total sales amount  
- `ship-city`, `ship-state`, `ship-country` – Shipping details  

## 🚀 Features
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Sales trend analysis
- Category and size distribution analysis
- Fulfilment & sales channel insights
- Visualizations (bar plots, count plots, heatmaps)

***📊 Exploratory Data Analysis (EDA)***

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt 
%matplotlib inline
import seaborn as sns
df=pd.read_csv(r'C:\Users\vikas\OneDrive\Documents\codes\python project\Python_Amazon_Sales_Analysis-main\Amazon Sale Report.csv',encoding= 'unicode_escape')
df.head(5)
df.tail(5)
df.columns
Index(['index', 'Order ID', 'Date', 'Status', 'Fulfilment', 'Sales Channel',
       'ship-service-level', 'Category', 'Size', 'Courier Status', 'Qty',
       'currency', 'Amount', 'ship-city', 'ship-state', 'ship-postal-code',
       'ship-country', 'B2B', 'fulfilled-by'],
      dtype='object')

ax=sns.countplot(x='Size' ,data=df)

for bars in ax.containers:
    ax.bar_label(bars)
```
![logo](https://github.com/user-attachments/assets/a5b4ef28-3839-4f9f-aaee-0fb81ccd2e4e)

```python
plt.figure(figsize=(10,5))

ax=sns.countplot(data=df, x='Courier Status',hue= 'Status')

plt.show()

```
![logo](https://github.com/user-attachments/assets/80d90eba-d5f1-4f7f-a517-5793cfeb3f77)

```python
df['Category'] = df['Category'].astype(str)
column_data = df['Category']
plt.figure(figsize=(10, 5))
plt.hist(column_data, bins=30, edgecolor='Black')
plt.xticks(rotation=90)
plt.show()

````
![logo](https://github.com/user-attachments/assets/4a29a339-a200-46b5-a62d-9ebc0dc8cccf)

```python
# top_10_States 
top_10_state = df['ship-state'].value_counts().head(10)
# Plot count of cities by state
plt.figure(figsize=(12, 6))
sns.countplot(data=df[df['ship-state'].isin(top_10_state.index)], x='ship-state')
plt.xlabel('ship-state')
plt.ylabel('count')
plt.title('Distribution of  State')
plt.xticks(rotation=45)
plt.show()

```
![logo](https://github.com/user-attachments/assets/ec4b638c-e18a-4856-8f19-ed7700efdece)

## Conclusion -

The data analysis reveals that the business has a significant customer base in Maharashtra state, mainly serves retailers, fulfills orders through Amazon, experiences high demand for T-shirts, and sees M-Size as the preferred choice among buyers.

