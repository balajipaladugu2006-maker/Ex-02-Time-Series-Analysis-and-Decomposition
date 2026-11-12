# Ex-02-Time-Series-Analysis-and-Decomposition

## NAME : Paladugu Venkata Balaji
## REG NO : 2305001024

## Aim
To perform time series analysis and decomposition on the monthly average temperature of a city using Python.

## Objectives
To create monthly temperature time-series data using Pandas.
To visualize the temperature variations using Matplotlib.
To decompose the time series into observed, trend, seasonal, and residual components using the seasonal_decompose() function.
To understand the different components of additive time series decomposition.

## Program:

~~~python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Create monthly temperature data
temperature = [
    25, 27, 29, 32, 34, 33,
    32, 31, 30, 29, 27, 25
]

# Step 2: Create date index
dates = pd.date_range(
    start="2025-01-01",
    periods=12,
    freq="ME"
)

# Step 3: Create time series
data = pd.Series(temperature, index=dates)

# Step 4: Display data
print("Monthly Temperature:")
print(data)

# Step 5: Plot original time series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="o")
plt.title("Monthly Average Temperature")
plt.xlabel("Month")
plt.ylabel("Temperature (°C)")
plt.grid()
plt.show()

# Step 6: Decompose the time series
result = seasonal_decompose(
    data,
    model="additive",
    period=12
)

# Step 7: Display decomposition
result.plot()
plt.show()

~~~

## Output:
<img width="382" height="380" alt="image" src="https://github.com/user-attachments/assets/6a960fef-efb9-4849-8767-17941025b7c2" />
<img width="1042" height="582" alt="image" src="https://github.com/user-attachments/assets/988175e3-541d-4bf2-b8ce-1df189ab400f" />
<img width="891" height="597" alt="image" src="https://github.com/user-attachments/assets/02edd458-1cc4-4b02-a06d-a9b09e44ed58" />

## Result
The monthly temperature time series was successfully plotted and decomposed into observed, trend, seasonal, and residual components using Python.
