---
layout: post
title: "Zero to hero in Model building using Python!"
published: true
---


We belive you won't learn data science unless you start doing it by yourself. So don't copy paste this code try to write it. This activity will improve your muscle memory and will help to retain knowledge for long.

## **Model building steps using Python:**
 
##**Loading the data**
import pandas as pd
train = pd.read_csv('train.csv')
test = pd.read_csv('test.csv')

## **Univariate Analysis:**
Here we will explore all varibles one by one. Method to perform univariate analysis will depend on whether the variable type is caltagorical or continious. So lets consider those individually.

#let's start by looking at the data type of each column
train.dtypes
print  train.dtypes

> ID                 int64
Age                int64
Workclass         object
Education         object
Marital.Status    object
Occupation        object
Relationship      object
Race              object
Sex               object
Hours.Per.Week     int64
Native.Country    object
Income.Group      object
dtype: object

> Here we can see that there are 3 continuous variables and 9 categorical variables, where the last one(Income group) is the outcome itself. Let's perform univariate analysis on each type.

##

1.Continuous Variable :
In case of continuous variables, we generally focus on measure of central tendency and spread of data such as Mean,Median,Range,IQR and Standard Deviation. Let's implement them using pandas in python.

Pandas dataframes have an inbuilt routine called describe which does the job.
In[16]:train.describe()
Out[16]: 
                 ID           Age  Hours.Per.Week
count  32561.000000  32561.000000    32561.000000
mean   16281.000000     38.581647       40.437456
std     9399.695394     13.640433       12.347429
min        1.000000     17.000000        1.000000
25%     8141.000000     28.000000       40.000000
50%    16281.000000     37.000000       40.000000
75%    24421.000000     48.000000       45.000000
max    32561.000000     90.000000       99.000000






