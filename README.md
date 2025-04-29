# GDP-Pilot-Analysis-using-World-Bank-Data
This is a pilot project where we analyze GDP data for selected countries using **SQL**, **Python**, and **Tableau**. The goal is to understand GDP trends, compare between countries, and build visualizations for presentation.

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

#Key Features:

Line Chart: Visualizes the annual GDP changes for all three countries.

Interactive Filters: Allows selection of specific years or countries for focused analysis.

Tooltips: Hovering over each data point reveals exact GDP values and growth rates for that year.


#Insights:

Bangladesh shows a notable increase in GDP between 2021 and 2022, indicating a strong post-pandemic recovery.

India experienced a sharp rebound in 2021, reflecting rapid economic recovery.

USA maintains the highest GDP among the three, with consistent and stable growth over the observed period.


This visualization helps users compare and understand country-wise economic performance and recovery patterns following the global pandemic.


___



## Step 3: Tableau Dashboard Visualization

After SQL filtering and Python-based analysis, we created a dynamic and interactive dashboard using Tableau to visually explore GDP trends.

### Key Features of the Dashboard:
- **Line Chart:** Displays GDP growth from 2020 to 2022 for Bangladesh, India, and USA.
- **Filter Options:** Year-wise and Country-wise filters to customize views.
- **Interactive Tooltips:** Hovering over any point shows exact GDP values and growth rates.

### Tableau Screenshot:

![Tableau GDP Dashboard](images/tableau_gdp_dashboard.png)

*(Replace this image with a real screenshot of your Tableau dashboard)*

### Insights Gained from Dashboard:
- Bangladesh's GDP has shown a strong growth trajectory post-2020.
- India's GDP rebounded sharply in 2021, showing recovery from pandemic impacts.
- The USA shows steady growth, maintaining its lead as the world’s largest economy.

### Tableau File:
You can find the Tableau dashboard in the following location:
