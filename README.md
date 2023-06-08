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
### Reading data from database(csv file)
```js 
  #Import data from csv file
  data=pd.read_csv("covid-data.csv")
  
  data.head()
```
```

iso_code	location	date	total_cases	new_cases	total_deaths	new_deaths	total_cases_per_million	new_cases_per_million	total_deaths_per_million	...	aged_65_older	aged_70_older	gdp_per_capita	extreme_poverty	cvd_death_rate	diabetes_prevalence	female_smokers	male_smokers	handwashing_facilities	hospital_beds_per_100k
0	ABW	Aruba	2020-03-13	2	2	0	0	18.733	18.733	0.0	...	13.085	7.452	35973.781	NaN	NaN	11.62	NaN	NaN	NaN	NaN
1	ABW	Aruba	2020-03-20	4	2	0	0	37.465	18.733	0.0	...	13.085	7.452	35973.781	NaN	NaN	11.62	NaN	NaN	NaN	NaN
2	ABW	Aruba	2020-03-24	12	8	0	0	112.395	74.930	0.0	...	13.085	7.452	35973.781	NaN	NaN	11.62	NaN	NaN	NaN	NaN
3	ABW	Aruba	2020-03-25	17	5	0	0	159.227	46.831	0.0	...	13.085	7.452	35973.781	NaN	NaN	11.62	NaN	NaN	NaN	NaN
4	ABW	Aruba	2020-03-26	19	2	0	0	177.959	18.733	0.0	...	13.085	7.452	35973.781	NaN	NaN	11.62	NaN	NaN	NaN	NaN
5 rows × 32 columns

(19496, 32)
Canada            146
United States     146
Japan             146
Mexico            146
China             146
                 ... 
Yemen              45
Western Sahara     29
Tajikistan         24
Comoros            23
Lesotho            10
Name: location, Length: 212, dtype: int64
iso_code                            True
location                           False
date                               False
total_cases                        False
new_cases                          False
total_deaths                       False
new_deaths                         False
total_cases_per_million             True
new_cases_per_million               True
total_deaths_per_million            True
new_deaths_per_million              True
total_tests                         True
new_tests                           True
total_tests_per_thousand            True
new_tests_per_thousand              True
new_tests_smoothed                  True
new_tests_smoothed_per_thousand     True
tests_units                         True
stringency_index                    True
population                          True
population_density                  True
median_age                          True
aged_65_older                       True
aged_70_older                       True
gdp_per_capita                      True
...
female_smokers                      True
male_smokers                        True
handwashing_facilities              True
hospital_beds_per_100k              True
dtype: bool
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
iso_code                              64
location                               0
date                                   0
total_cases                            0
new_cases                              0
total_deaths                           0
new_deaths                             0
total_cases_per_million              377
new_cases_per_million                377
total_deaths_per_million             377
new_deaths_per_million               377
total_tests                        14332
new_tests                          14904
total_tests_per_thousand           14332
new_tests_per_thousand             14904
new_tests_smoothed                 13866
new_tests_smoothed_per_thousand    13866
tests_units                        13267
stringency_index                    4500
population                            64
population_density                   850
median_age                          1743
aged_65_older                       1980
aged_70_older                       1832
gdp_per_capita                      1982
...
female_smokers                      5052
male_smokers                        5206
handwashing_facilities             11822
hospital_beds_per_100k              3160
dtype: int64
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
```
