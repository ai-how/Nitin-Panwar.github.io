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

ID                 int64
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





