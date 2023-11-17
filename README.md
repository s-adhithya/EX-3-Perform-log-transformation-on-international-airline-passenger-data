# EX-3-Perform-log-transformation-on-international-airline-passenger-data
## AIM:
To Write a Program to log transformation on international airline passenger data

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook
## Procedure:
1.import the numpy ,pandas and matplotlib.pyplot modules

2.read the dataset using pandas

3.applying log transformation for dataset

4.Plot the trend dataset 

5.plot the log transformation data

## Program:
```
import pandas as pd
import numpy as np
import matplotlib.pylab as plt
%matplotlib inline
from matplotlib.pylab import rcParams
from datetime import datetime
data=pd.read_csv(r'/content/AirPassengers.csv')
data.head()

data.tail()

data.shape

data['Month']=pd.to_datetime(data['Month'], infer_datetime_format=True)
data=data.set_index(['Month'])
data

plt.figure(figsize=(20,10))
plt.xlabel("Month")
plt.ylabel("Air Passengers Count")
plt.plot(data)

trend = data['#Passengers'].rolling(window=12).mean()

# Plot the trend
plt.plot(trend)
plt.xlabel('Month')
plt.ylabel('Trend')
plt.show()

seasonality = data['#Passengers'] - trend
# Plot the seasonality
plt.plot(seasonality)
plt.xlabel('Month')
plt.ylabel('Seasonality')
plt.show()

# @title
# Apply log transformation to the data
log_data = np.log(data)

# Plot the original data and the log-transformed data
import matplotlib.pyplot as plt
#plt.hist(data, bins=50, label='Original Data')

plt.plot(log_data)
plt.legend()
plt.show()
```
## Output:
### data.head()
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/7c7285aa-8894-4b7e-ae51-51a918eacf50)


### data.tail()
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/87f9504c-313c-4d04-8250-0170bb25d120)


### data.shape
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/60493f95-8f95-4728-880a-711c900c69d4)


### data
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/ffc31b0b-f701-4f68-ba15-245335d0ee0f)


### Graph for datasets
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/09a8b9b9-ed2c-45f7-9afc-5bbc49e91694)


### Trend graph
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/6426b37b-a745-4c98-bd16-82531dc9b389)


### seasonality graph
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/779b2cee-7c67-41b7-9a18-c64878c25837)


### log-transformed data
![image](https://github.com/s-adhithya/EX-3-Perform-log-transformation-on-international-airline-passenger-data/assets/113497423/9423cfa6-9141-4829-a016-919bd339ae69)


## Result:
Thus the program to t log transformation on international airline passenger data is written and verified using python programming.
