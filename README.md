# **Amazon Sales Analysis 📺**  

### 🚀 **Technologies Used:** Python | Jupyter Notebook | Pandas | NumPy  | Matplotlib |Seaborn

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
![Screenshot 2025-09-15 142322](https://github.com/vikash-013/Amazon-Sales-Analysis/blob/main/Screenshot%202025-09-15%20142322.png)
    
