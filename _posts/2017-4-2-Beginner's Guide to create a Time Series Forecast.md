---
layout: post
title: Beginner's Guide to create a Time Series Forecast in Python
published: true
---

TS(Time Series) is considered to be one of the less known skill in the analytics space. Time series is a collection of data points collected at constant time intervals. But what makes a TS different from regular regression problem are- 

1. It is time dependent, so the basic assumption of linear regression model that the observations are independent doesn't hold in this case.
2. Along with an increasing or decreasing trends, most TS have some form of seasionality trends. For example. If you see the sales of woolen jacket over time, you will invariably find higher sales in winter season. 

Pandas has dedicated libraries for handling TS objects, particullarly the datetime64[ns] which stores time information and allows us to perform some operations really fast. Let's start by firing up the required libraries.

```
import pandas as pd
import numpy as np
import matplotlib.pylab as plt
%matplotlib inline
from matplotlib.pylab import rcParams
rcParams['figure.figsize'] = 15, 6
```





