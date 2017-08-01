---
layout: post
title: Kibana Timelion for Time Series Analysis
published: true
---


Kibana is very popular nowdays to visualize the Elastic search data but one aspect that Kibana falls short is in time series analysis and visualization. 
This is precisely where Timelion comes into picture. 
Timelion enables you to combine independent data sources within the same visualization.It uses straight forward query syntax. 


## Installing Timelion 
Since Timelion is built into Kibana, there is no need in taking any additional installation and setup steps. All you need is just data. 

## Timelion Expressions 
Timelion also has its query syntax, that is easy to use and very straight forward. It will not much of your time to get started with the Timelion query syntax. 

To get started, just open the Timelion in Kiabana and write the query 
''' 
.es(*)
'''







To start, you need to define only three paramaters in Timelion query-
1. Index- Index of the data that you want to explore
2. Timestamp- What is the column name of the timestamp field
3. metric- what you want to visulalize 




