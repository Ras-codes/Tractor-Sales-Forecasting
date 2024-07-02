<div align="center">
  <h1>Tractor Sales Forecasting</h1>
</div>


<div align="center">
Forecasting tractor sales using monthly data to predict future sales trends and optimize inventory management.
</div>



<div align="center">
  <img src="https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/8b60ec1a-23e4-4de3-bc9d-cd5c53210ca8">
</div>



## Tools

- **Programming Language**: Python 🐍
- **IDE**: Jupyter Notebook 📓
- **Data Manipulation and Analysis**:
  - NumPy 📊
  - pandas 🐼
- **Data Visualization**:
  - Matplotlib 📊

 
## Dataset Description: 

### Table- diabetes


### Variables-

| Variable Name                        | Data Type | Description                                                                        |
|--------------------------------------|-----------|------------------------------------------------------------------------------------|
| Month-Year                           | chr       | Represents the specific month and year of observation                              |
| Number of Tractor Sold               | int       | Indicates the quantity of tractors sold within the corresponding month-year period |


# ------------------------------------------------------------------------------


# Forecasting

This project uses Python to predict Tractor Sales. It covers everything from cleaning and preparing data to using advanced techniques for forecasting. You'll find Jupyter notebooks that explain each step, datasets to practice with, and examples showing how to visualize and analyze the data using Pandas, NumPy, Matplotlib, and Seaborn.


# ------------------------------------------------------------------------------


# Insights from the Dataset

- After importing the dataset, our first step is to check if the data is imported properly
- We can use `sales` to display the top few and last few observations of the dataset
- ![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/9744b569-3600-4347-ba61-ec5e5faeb317)
- To understand more about the data, including the number of non-null records in each columns, their data types, the memory usage of the dataset, we use `sales.info()`
- ![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/343f6365-87d7-45a7-a7ab-a33fada0b345)
- which means that the dataset contains 144 records and 2 variables.


# ------------------------------------------------------------------------------


# Modifying the Dataset

````
sales['year'] = sales.Month_Year.dt.year
sales['month'] = sales.Month_Year.dt.month
````
- Creating 'year' and 'month' columns allows for easy grouping and seasonal analysis.
- Checking Tractor Sales plot
````
ts = sales.No_Tractors_Sold
ts.plot()
````
![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/b6652529-a73b-4e7a-b5e4-20c1c3fbbe50)


# ------------------------------------------------------------------------------

## 1. Yearly Data Visualisation

 - Pivot table to summarizes the 'No_Tractors_Sold' data across different months and years, allowing for easy visualization and analysis of tractor sales trends over time.
![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/79873c55-ae00-4a5b-92cd-c8f1549e4b02)
- Visual representation of how tractor sales vary by month-year combinations, helping to identify trends and patterns over time.
````
pd.pivot_table(data = sales, index = 'year', columns = 'month', values = 'No_Tractors_Sold').plot(legend=False)
````
![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/f738bd6b-0e50-4521-a749-877f9d2631a2)

## 2. Monthly Data Visualisation

- Structured view of how tractor sales vary monthly over multiple years, providing insights into seasonal patterns and year-over-year trends.
![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/46d6f6ae-163a-4af2-9a8c-f4cab39af22a)
- Visual representation of how tractor sales vary monthly over time, highlighting any seasonal patterns or trends.
````
pd.pivot_table(data = sales, index = 'month', columns = 'year', values = 'No_Tractors_Sold').plot(legend=False)
````
![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/c7244048-ee68-42e0-82e8-52573331658d)

## 3. Seasonal Decomposition Visualisation

![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/b4176a5b-eab0-45d7-87b1-1124f7c02556)![image](https://github.com/Ras-codes/Tractor-Sales-Forecasting/assets/164164852/d517244e-9298-4b2f-84f0-b589f07a5583)
- Observed plot: Represents the actual raw data points of a time series, showing the original values observed over time without any decomposition into trend, seasonal, or residual components.
- Trend Plot: Shows the trend component extracted from the time series data, which represents the long-term behavior or direction of the data over time.
- Seasonal Plot: Displays the seasonal component, which represents the periodic patterns or fluctuations that recur at fixed intervals within the data.
- Residual Plot: Illustrates the residual component, capturing the random variations or noise left after removing the trend and seasonal components.



































































