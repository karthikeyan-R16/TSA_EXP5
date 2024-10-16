# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average Rainfall

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/rainfall.csv')
print("FIRST FIVE ROWS:")
print(data.head())
data = data.head(120)  # Adjust this number as per your dataset's requirement
data['Date'] = pd.date_range(start='1/1/2010', periods=len(data), freq='M')
data.set_index('Date', inplace=True)

# Replace 'Price' with the actual column name containing your data, e.g., 'rainfall'
result = seasonal_decompose(data['rainfall'], model='additive', period=12) 

print("\nPLOTTING THE DATA:")
plt.figure(figsize=(10, 5))

# Replace 'Price' with the actual column name, e.g., 'rainfall'
plt.plot(data['rainfall']) 

plt.title('Yearly Average rainfall Over Time') # Update title accordingly
plt.xlabel('Year')
plt.ylabel('rainfall') # Update y-axis label accordingly
plt.show()

print("\nSEASONAL PLOT REPRESENTATION:")
plt.figure(figsize=(10, 5))
result.seasonal.plot()
plt.title('Seasonal Decomposition')
plt.ylabel('Seasonal Component')
plt.show()
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/rainfall.csv')
print("FIRST FIVE ROWS:")
print(data.head())
data = data.head(120)  # Adjust this number as per your dataset's requirement
data['Date'] = pd.date_range(start='1/1/2010', periods=len(data), freq='M')
data.set_index('Date', inplace=True)

# Replace 'Price' with the actual column name containing your data, e.g., 'rainfall'
result = seasonal_decompose(data['rainfall'], model='additive', period=12) 

print("\nPLOTTING THE DATA:")
plt.figure(figsize=(10, 5))

# Replace 'Price' with the actual column name, e.g., 'rainfall'
plt.plot(data['rainfall']) 

plt.title('Yearly Average rainfall Over Time') # Update title accordingly
plt.xlabel('Year')
plt.ylabel('rainfall') # Update y-axis label accordingly
plt.show()

print("\nSEASONAL PLOT REPRESENTATION:")
plt.figure(figsize=(10, 5))
result.seasonal.plot()
plt.title('Seasonal Decomposition')
plt.ylabel('Seasonal Component')
plt.show()

print("\nTREND PLOT REPRESENTATION:")
plt.figure(figsize=(10, 5))
result.trend.plot()
plt.title('Trend Decomposition')
plt.ylabel('Trend Component')
plt.show()
```
### OUTPUT:
FIRST FIVE ROWS:

![image](https://github.com/user-attachments/assets/30fa77ae-6911-4587-a6c5-4eabe0cbd3ec)


PLOTTING THE DATA:
![image](https://github.com/user-attachments/assets/dc40f920-931d-4350-a13e-139d07a470c6)


SEASONAL PLOT REPRESENTATION :

![image](https://github.com/user-attachments/assets/0984e046-ead4-4693-a9ac-8bc7ed166e20)



TREND PLOT REPRESENTATION :

![image](https://github.com/user-attachments/assets/9cbe8c24-b39f-46fe-88b7-738c61c297d2)

OVERAL REPRESENTATION:

![image](https://github.com/user-attachments/assets/ced3f798-6f9a-45b2-9225-ca60b3896d46)



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
