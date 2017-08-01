---
layout: post
title: Kibana Timelion for Time Series Analysis
published: true
---


Kibana is very popular nowdays to visualize the Elastic search data but one aspect that Kibana falls short is in time series analysis and visualization. This is precisely where Timelion comes into picture. 

## Timelion
Timelion enables you to combine independent time series data within the same visualization. It offers you a lot of functions to manupulate the data. It uses straight forward query syntax. 


## Installing Timelion 
Since Timelion is built into Kibana, there is no need in taking any additional installation and setup steps. All you need is just indexed data. 

## Timelion Expressions 
Timelion also has its query syntax, that is easy to use and very straight forward. It will not much of your time to get started with the Timelion query syntax. 

To get started, just open the Timelion in Kiabana and hit the below query 
```
.es(*)
```
This will return all the available indexed data.
![](http://i.imgur.com/bK0L0dd.png)

If you want to explore specific index data then you need to specify the index name e.g
```
.es(index='elastalert_*',timefield='starttime')
```
![](http://i.imgur.com/TUGKlL6.png)


## offset 
Offset is used when you wnat to offset the series retrieval by a date/time expression. 
In this example you will be able to offset the data back one day. 
```
.es(index='elastalert_*',timefield='starttime'), .es(index='elastalert_*',timefield='starttime', offset=-1d),
```
![](http://i.imgur.com/q7KMOvL.png)

It is bit hard to differntiate the two series, so lets go ahead and add the label for each of the series for the better understanding purpose. 
```
.es(index='elastalert_*',timefield='starttime').label('current day'), .es(index='elastalert_*',timefield='starttime', offset=-1d).label('previous day')
```
![](http://i.imgur.com/0hlUaPj.png)

Timelion provides a lot of other functionality. 
## title()
we can add the title for the visualization very easily by just appending it to .es() query
```
.es(index='elastalert_*',timefield='starttime').label('current day'), .es(index='elastalert_*',timefield='starttime', offset=-1d).label('previous day').title('Experiments with timelion')
```
![](http://i.imgur.com/iwRJfTb.png)

## lines()

To visualize data and to differntiate one series from another, we can use lines() function. You can pass the paramenters like fill, width to lines() function. e.g
```
.es(index='elastalert_*',timefield='starttime').label('current day').lines(fill=1,width=0.5).color(gray), .es(index='elastalert_*',timefield='starttime', offset=-1d).label('previous day').title('Experiments with timelion').lines(fill=0,width=1).color(red)
```
![](http://i.imgur.com/6mLfKan.png)

## Mathematics functions
Let's do the mathematical operation by adding one more visualization

.derivative()
.multiply()
.divide()

## Conditional operators
In this section we will see how to modify time series data with conditional logic and create a trend with a moving average. This is helpful to easily detect outliers and patterns over time. 

To configure threshold we will nedd if() to compare each point to number, adjust the styling if the column evaluates to true and use the default styling if the condition evaluates to false. 

eq- equal
ne- not equal 
lt- less than
lte- less than or equal to 
gt- greater than 
gte- greater than or equal to 

```
.es(index='elastalert_*'),.es(index='elastalert_*').if(gt,60,.es(index='elastalert_*'),null).label('alert').color('red')
```
![](http://i.imgur.com/NeUu4qk.png)

There are other functionalities also available like calculate moving avg etc. 









