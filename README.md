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
```
      Africa           39857
      Europe           37494
      Asia             36584
      North America    25203
      South America     9621
      Oceania           9345

### Line graph of Total cases in India
We can clearly see that in after summer the total cases of corona virus in India was increasing.

![image](https://github.com/asbpintu/Covid-19-Outbreak-Prediction-World-data-and-INDIA-data-/assets/77091963/858eb982-6f53-4dff-8865-fa2f1d9470a0)


