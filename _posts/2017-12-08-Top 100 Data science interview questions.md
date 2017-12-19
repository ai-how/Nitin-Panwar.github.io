---
layout: post
title: Top 100 Data science interview questions
published: true
---

Data science, also knowns as data-driven decision, is an interdisciplinery field about scientific methods, procss and systems to extract knowledge from data in various forms, and take descision based on this knowledge. A data scientist should not be evaluated only on his/her knowledge on mahine learning, but he/she should also have good expertise on statistics. 
I will try to start from very basics of data science and then slowly move to expert level. So let's get started.

## 1. What is bias, variance trade off ?
#### Bias:  
"Bias is error introduced in your model due to over simplification of machine learning algorithm." 
It can lead to underfitting. When you train your model at that time model makes simplified assumptions to make the target function easier to understand.
##### Low bias machine learning algorithms - Decision Trees, k-NN and SVM 
##### Hight bias machine learning algorithms - Liear Regression, Logistic Regression

#### Variance: 
"Variance is error introduced in your model due to complex machine learning algorithm, your model learns noise also from the training dataset and performs bad on test dataset."
It can lead high sensitivity and overfitting.

#### Bias, Variance trade off:
The goal of any supervised machine learning algorithm is to have low bias and low variance to achive good prediction performance.
1. The k-nearest neighbors algorithm has low bias and high variance, but the trade-off can be changed by increasing the value of k which increases the number of neighbors that contribute to the prediction and in turn increases the bias of the model.

2. The support vector machine algorithm has low bias and high variance, but the trade-off can be changed by increasing the C parameter that influences the number of violations of the margin allowed in the training data which increases the bias but decreases the variance.

There is no escaping the relationship between bias and variance in machine learning.

Increasing the bias will decrease the variance.
Increasing the variance will decrease the bias.


## 2. What is exploding gradients ?
"Exploding gradients are a problem where __large error gradients__ accumulate and result in very large updates to neural network model weights during training."
At an extreme, the values of weights can become so large as to overflow and result in NaN values.

This has the effect of your model being unstable and unable to learn from your training data. 
Now let's understand what is the gradient.
#### Gradient: 
Gradient is the __direction and magnitude__ calculated during training of a neural network that is used to update the network weights in the right direction and by the right amount. 


## 3.  What is the difference between supervised and unsupervised machine learning?
#### Supervised Machine learning:
Supervised machine learning requires training labeled data. 
#### Unsupervised Machine learning: 
Unsupervised machine learning doesn't required labeled data. 

### 4. How KNN supervised machine learning algorithm works?




