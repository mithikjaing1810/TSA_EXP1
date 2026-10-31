# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 31-10-2026
###  Reg no: 212224240087

### Dataset : Nvidia stock price 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
   
# PROGRAM:
```
import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv("/content/NVIDIA_STOCK.csv")

df = df.iloc[2:].copy()

df['Price'] = pd.to_datetime(df['Price'])
df['Close'] = pd.to_numeric(df['Close'], errors='coerce')

df.set_index('Price', inplace=True)

df_resampled = df['Close'].resample('D').interpolate()

df_resampled.plot(
    kind='line',
    label='NVIDIA Stock Price',
    color='black'
)

plt.title('Time Series Plot of NVIDIA Stock Price')
plt.xlabel('Year')
plt.ylabel('Stock Closing Price')
plt.legend()
plt.grid(True)
plt.show()
```

# OUTPUT:

<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/31a6e964-9377-4f55-937b-2eee9d884ec9" />





# RESULT:
Thus we have created the python code for plotting the time series of given data.
