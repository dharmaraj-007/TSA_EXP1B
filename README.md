# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
df=pd.read_csv('train.csv')
```
# REGULAR DIFFERENCING:
```
df_diff = df.diff().dropna()
plt.figure(figsize=(12, 6))
plt.plot(df_diff, label="First-Order Differenced Data", color="green")
plt.title("Regular Differencing (First-Order)")
plt.xlabel("Order Date")
plt.ylabel("Sales Difference")
plt.legend()
plt.show()
```
# SEASONAL ADJUSTMENT:
```
df_seasonal_diff = df.diff(7).dropna()
plt.figure(figsize=(12, 6))
plt.plot(df_seasonal_diff, label="Seasonally Adjusted Data (7-day Difference)", color="purple")
plt.title("Seasonal Adjustment (Weekly Differencing)")
plt.xlabel("Order Date")
plt.ylabel("Sales Difference")
plt.legend()
plt.show()
```
# LOG TRANSFORMATION:
```
import numpy as np
df_log = np.log(df[df > 0])  
plt.figure(figsize=(12, 6))
plt.plot(df_log, label="Log-Transformed Sales", color="red")
plt.title("Log Transformation of Sales Data")
plt.xlabel("Order Date")
plt.ylabel("Log(Sales)")
plt.legend()
plt.show()
```
### OUTPUT:


REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/0d3ca054-a7cc-4570-a29d-ada3b3146caa)


SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/3f26b736-8fa7-4f59-abae-e179f82063ef)


LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/0183b96c-a016-4649-b9c1-f221a610c1cb)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
