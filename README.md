# **📈 Economic Recovery Through GDP: A Data Story**
  

## **Introduction**  

After the global economic disruptions of 2020, GDP trends became a key indicator of recovery. Some nations rebounded rapidly, while others experienced steady but slower growth. Understanding GDP dynamics helps uncover **economic resilience, policy impacts, and long-term growth trajectories**.  

This study explores the GDP trends of **Bangladesh, India, and the USA** from **2020 to 2022** using **SQL, Python, and Tableau**, highlighting key shifts in their economic journeys.  

## **Why GDP Trends Matter**  

- **📈 Bangladesh:** Steady post-pandemic growth, showcasing resilience in emerging economies.  
- **🚀 India:** A sharp GDP rebound in 2021, reflecting rapid economic recovery strategies.  
- **🏛️ USA:** Continued stable growth, maintaining its role as the world’s largest economy.  

By combining **data-driven storytelling** with **advanced visualization techniques**, this project transforms raw GDP numbers into **actionable insights** for better economic analysis.


![GDP Comparison Dashboard](https://github.com/almazid82/GDP-Pilot-Analysis-using-World-Bank-Data/blob/main/Screenshot_20250429-142013%7E2.png?raw=true)


---


## 1. Dataset Description

**Source:** [World Bank Open Data](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD)  
**Indicator:** GDP (current US$)  
**Format:** CSV  
**Countries:** Bangladesh, India, China, USA  
**Time Range:** 2000 - 2022

Dataset path: `data/world_gdp.csv`

---

## 2. Step-by-Step Workflow

### Step 1: SQL for Data Filtering

We use SQL to filter GDP data by country and time range.

**Sample SQL Query:**
```sql
SELECT country_name, year, gdp
FROM world_gdp
WHERE country_name IN ('Bangladesh', 'India', 'USA')
AND year BETWEEN 2000 AND 2022;
```

____

**SQL output is :**

Country Name | Year | GDP (Current US$)     |
|--------------|------|------------------------|
| Bangladesh   | 2020 | 302571000000           |
| Bangladesh   | 2021 | 416264000000           |
| Bangladesh   | 2022 | 460000000000           |
| India        | 2020 | 2668670000000          |
| India        | 2021 | 3176290000000          |
| India        | 2022 | 3393000000000          |
| USA          | 2020 | 20937000000000         |
| USA          | 2021 | 23151000000000         |
| USA          | 2022 | 25460000000000         |


---
### SQL Output Explanation

The table above displays the GDP (in current US dollars) for Bangladesh, India, and the USA from 2020 to 2022. This data was extracted using a SQL query that filters the dataset based on:

- Selected Countries: Bangladesh, India, USA
- Selected Years: 2020, 2021, and 2022

#### Key Insights:
- **Bangladesh** shows a consistent increase in GDP from $302.6B in 2020 to $460B in 2022.
- **India** also demonstrates strong growth, reaching over $3.39 trillion in 2022.
- **USA** remains the largest economy, crossing $25 trillion GDP in 2022.

This filtered dataset will be used in the next steps for Python-based visualization and Tableau dashboard creation.


---




## Step 2: Python for Analysis and Visualization

After filtering the dataset using SQL, we use Python (pandas, matplotlib) to analyze and visualize the GDP trends of Bangladesh, India, and the USA.

### Python Libraries Used:
- pandas
- matplotlib
- seaborn *(optional)*

### Python Code:
```python
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv('data/world_gdp.csv')

# Filter for selected countries and years
df = df[df['Country Name'].isin(['Bangladesh', 'India', 'USA'])]
df = df[(df['Year'] >= 2020) & (df['Year'] <= 2022)]

# Pivot for visualization
pivot_df = df.pivot(index='Year', columns='Country Name', values='GDP')

# Plot the GDP trend
pivot_df.plot(figsize=(10, 6), marker='o')
plt.title("GDP Trend (2020-2022): Bangladesh vs India vs USA")
plt.ylabel("GDP in Current US Dollars")
plt.xlabel("Year")
plt.grid(True)
plt.tight_layout()
plt.show()
```
____
![GDP Dashboard](https://github.com/almazid82/GDP-Pilot-Analysis-using-World-Bank-Data/blob/main/Screenshot_20250429-141132%7E2.png?raw=true)
## Description & Analysis:

This visualization presents GDP growth trends from 2020 to 2022 for Bangladesh, India, and the United States.

### Key Features:

Line Chart: Visualizes the annual GDP changes for all three countries.

Interactive Filters: Allows selection of specific years or countries for focused analysis.

Tooltips: Hovering over each data point reveals exact GDP values and growth rates for that year.


#### Insights:

Bangladesh shows a notable increase in GDP between 2021 and 2022, indicating a strong post-pandemic recovery.

India experienced a sharp rebound in 2021, reflecting rapid economic recovery.

USA maintains the highest GDP among the three, with consistent and stable growth over the observed period.


This visualization helps users compare and understand country-wise economic performance and recovery patterns following the global pandemic.


___



## Step 3: Tableau Dashboard Visualization

After SQL filtering and Python-based analysis, we created a dynamic and interactive dashboard using Tableau to visually explore GDP trends.

## **Creating a Tableau GDP Dashboard (2020–2022)**

### **Step 1: Import the Data**
1. Open **Tableau** and connect to the CSV file (`world_gdp.csv`).
2. Ensure the dataset contains:
   - **Country Name**
   - **Year**
   - **GDP (Current US$)**

### **Step 2: Create the Line Chart**
1. Drag **Year** to `Columns`.
2. Drag **GDP (Current US$)** to `Rows`.
3. Drag **Country Name** to `Color` to differentiate between Bangladesh, India, and USA.
4. Change the chart type to **Line Chart**.
5. Format:
   - Add **Gridlines** for better readability.
   - Use **Legible Axis Labels**.

### **Step 3: Add Filters for Interactivity**
1. Drag **Year** and **Country Name** to `Filters`.
2. Enable **Dropdown Selectors** so users can filter GDP trends interactively.

### **Step 4: Format & Style the Dashboard**
1. Add **Title:** `"GDP Trends Dashboard (2020–2022)"`.
2. Customize fonts, colors, and **tooltip settings**.
3. Enable **Hover Tooltips** showing GDP values per year.

### **Final Touches & Publishing**
1. Ensure interactivity works correctly.
2. **Save & Export** the dashboard.
3. Share insights based on trends:
   - **Bangladesh:** Steady growth post-2020.
   - **India:** Sharp GDP rise in 2021.
   - **USA:** Consistent economic expansion.

---

💡 *Following these steps ensures a professional, interactive GDP dashboard in Tableau!* 🚀

____


# **Final Decision: Purpose & Methodology of the GDP Analysis Project**

## **Project Purpose**
The objective of this project was to analyze GDP trends of selected countries—Bangladesh, India, and the USA—over **2020 to 2022** using structured **data-driven methodologies**. By combining analytical tools with visual storytelling, we aimed to uncover **economic patterns, recovery trends, and comparative insights**.

## **Why We Used SQL, Python, and Tableau?**

### **1. SQL – Data Extraction & Structuring**
- **Efficient filtering:** Extracted GDP values based on country and year.
- **Data consistency:** Ensured only relevant data was processed.
- **Optimized querying:** Allowed structured selection for deeper analysis.

### **2. Python – Data Analysis & Visualization**
- **Data transformation:** Cleaned and reshaped the dataset for visualization.
- **Trend analysis:** Used `pandas` and `matplotlib` for GDP comparisons.
- **Insights generation:** Revealed economic shifts through statistical computations.

### **3. Tableau – Interactive Data Exploration**
- **Dynamic dashboard:** Enabled real-time analysis with **filters & tooltips**.
- **Visual storytelling:** Made GDP trends **intuitive and accessible**.
- **User-driven exploration:** Allowed flexible comparison across years and countries.

## **Conclusion & Impact**
This project successfully demonstrates the power of **structured analysis and visualization** in understanding GDP trends. By integrating **SQL for data management, Python for computation, and Tableau for visualization**, we created a robust system to **explore economic changes interactively**.

This framework can be extended to **forecast future GDP trends**, **analyze additional economic indicators**, and **compare global financial markets**.

🚀 *This is just the beginning—data-driven insights open endless possibilities!*


____

## License

This content is shared for **educational and portfolio purposes only**.  
Licensed under the [MIT License](LICENSE) © 2025 Shamsul Al Mazid.

---

## Contact


[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/shamsul-al-mazid-073a87286?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/sondartara.tara.777)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shamsulalmazid@gmail.com)


📌 This project offers a data-driven glimpse into our climate future, serving as a valuable reference for researchers, policymakers, and anyone concerned about the planet.

___

## 🛠️ Tools & Technologies

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![SQL](https://img.shields.io/badge/SQL-005C84?style=for-the-badge&logo=sqlite&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91?style=for-the-badge&logo=visual%20studio&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Microsoft 365](https://img.shields.io/badge/Microsoft_365-D83B01?style=for-the-badge&logo=microsoft&logoColor=white)
![Google Workspace](https://img.shields.io/badge/Google_Workspace-4285F4?style=for-the-badge&logo=google&logoColor=white)




