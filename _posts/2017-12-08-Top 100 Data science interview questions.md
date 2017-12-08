---
layout: post
title: Top 100 Data science interview questions
published: true
---

Data science, also knowns as data-driven decision, is an interdisciplinery field about scientific methods, procss and systems to extract knowledge from data in various forms, and take descision based on this knowledge. A data scientist should not be evaluated only for his knowledge on mahine learning, but he should also have good expertise on statistics. I will try to start from very basics and then slowly move to expert level. So let's get started.

## 1. What is bias, variance trade off ?
#### Bias:  
"Bias is error introduced in your model due to over simplification of machine learning algorithm."
Let me simplify it for you, when you train your model at that time model makes simplifying assumptions to make the target function easier to understand.
Low bias machine learning algorithms - Decision Trees, k-NN and SVM 
Hight bias machine learning algorithms - Liear Regression, Logistic Regression

#### Variance: 
"Variance is error introduced in your model due to complex machine learning algorithm, your model learns noise also from the training dataset and perform bad on test dataset."

#### Bias, Variance trade off:
The goal of any supervised machine learning algorithm is to have low bias and low variance to achive good prediction performance.
1. The k-nearest neighbors algorithm has low bias and high variance, but the trade-off can be changed by increasing the value of k which increases the number of neighbors that contribute t the prediction and in turn increases the bias of the model.

2. The support vector machine algorithm has low bias and high variance, but the trade-off can be changed by increasing the C parameter that influences the number of violations of the margin allowed in the training data which increases the bias but decreases the variance.

There is no escaping the relationship between bias and variance in machine learning.

Increasing the bias will decrease the variance.
Increasing the variance will decrease the bias.


