---
layout: post
title:      "Random Forests Overview"
date:       2020-03-26 01:34:55 +0000
permalink:  random_forests_overview
---

The goals of this blog are

* Provide overview of random forest
* Advantages and disadvantages of random forest


Many folks ask their trusted friends their opinions to get their feedback about about the decisions that are making before making that final decision.  They are measuring those opinions by comparing and contrasted the different thoughts to ultimately try to make the best possible choices.  They also me be trying to get rid of their own bias by asking others.  I see this as a fun analogy to some machine learning algorithms.  One of the more common machine learning is Random Forest.  

A real quick description of the process of random forest.  Its ensemble method of a bunch of decision trees. A decision tree is a quasi flowchart or think of it as a series of if else rules classifying best outcomes.  Each node represents a test of some attribute of the data.   Each branch represents the outcome of the test.  Each leaf node represents a decision after computing all attributes. 
The final result is a tree with decision nodes and leaf nodes. A decision node (e.g., Outlook) has two or more branches (e.g., Sunny, Overcast and Rainy). Leaf node (e.g., Play) represents a decision or classification.
Please note that random forest algorithms don’t use decision splitters like information gain or mini because the process of finding the root node & spitting it the features happen at random.

One of the disadvantage of decision tree is overfitting the data and random forest can solve that issue.   A model that has learned the noise instead of the signal is considered “overfit” because it fits the training dataset well but has poor fit with other datasets like the test data.  Random forests involve building several decision trees of the data’s features and predicts with majority voting among decision trees for classification or averages for regression.  This can help solve issues of overfitting the data. See below for the flow for random forest

Advantages of  

* Provide Reliable feature importance.

* Little tuning of parameters with random forest models; whereas, models like Gradient-boosted have more hyper-params to tune.

* No data normalization and scaling needed as well as automatically manages missing values

* It has methods for balancing errors in data sets where classes are imbalanced.

* Works well with big datasets.  


Disadvantages of

* Overfitting can easily occur.

* Not good when there are rare outcomes or rare predictors; for example trying to predict customer behaviors when there’s highly unusual segments.

* When there’s many decision trees it can be difficult  to have an intuitive grasp of the relationship existing in the input data.

* As with many machine learning algorithms random forests are more of a black box domain, which can make it difficult to interpret model predictions.

* Random forests is definitely one of my favorite algorithms and not just because of their ease of use.  Many of my recent projects have been trying to find best features so this model has provided good results for them.  
