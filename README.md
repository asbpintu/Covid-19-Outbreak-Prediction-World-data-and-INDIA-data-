# Covid-19-Outbreak-Prediction-World-data-and-INDIA-data-

### Import necessary packages
```js
import numpy as np 
import matplotlib.pyplot as plt 
import matplotlib.colors as mcolors
import pandas as pd 
import random
import math
import time
from sklearn.linear_model import LinearRegression, BayesianRidge
from sklearn.model_selection import RandomizedSearchCV, train_test_split
from sklearn.preprocessing import PolynomialFeatures
from sklearn.svm import SVR
from sklearn.metrics import mean_squared_error, mean_absolute_error
import datetime
import operator 
%matplotlib inline
import warnings

plt.style.use('seaborn-poster')
warnings.filterwarnings("ignore")
```
### Reading data from database(csv file)
```js 
  #Import data from csv file
  data=pd.read_csv("covid-data.csv")
  
  data.head()
```
