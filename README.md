# Covid-19-Outbreak-Prediction-World-data-and-INDIA-data-

### Import necessary packages
```js
import numpy as np 
import matplotlib.pyplot as plt 
import matplotlib.colors as mcolors
import seaborn as sns
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
### Showing the total no of records grouped by Continent
```js 
      data["continent"].value_counts()
      
      Africa           39857
      Europe           37494
      Asia             36584
      North America    25203
      South America     9621
      Oceania           9345
```
