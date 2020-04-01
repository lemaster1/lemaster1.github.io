---
layout: post
title:      "XGBoost Overview"
date:       2020-04-01 01:02:12 +0000
permalink:  xgboost_overview
---

I recently saw a post or read an article that XGBoost has won more Kaggle data modeling competitions than any other machine learning algorithms.  More and more businesses are using this model.  10 to 15 years ago regression models were probably the most popular in business but I get the sense that XGBoost is fast becoming more popular now.  I wrote another blog about linear regression. 

When doing my research, I found this great summary of the different machine learning algorithms at the evolution of XGBoost at this blog:  https://towardsdatascience.com/https-medium-com-vishalmorde-xgboost-algorithm-long-she-may-rein-edd9f99be63d

The goal of this blog is just to provide an overview of XGBoost so that you’ll consider it along with the other machine learning models.  In addition, I am trying to explain it with not a lot of math references to provide a different explanation of it.   By the way, XGBoost is also referred to as extreme gradient boosting.  What a great title for some algorithms. 

**Overview and How it Works**

XGBoost is a decision tree based ensemble machine learning algorithm that uses a gradient boosting.  Gradient descent is an optimization algorithm that finds the optimal weights that reduces prediction error.  What?  Think of it as finding the best way down mountain where you are trying to optimize each step down it.  Picture starting at the top of the mountain staring down at your target.  Each step down you are recalculating on an iterative bases each negative gradient step.  This process continues until reaching the target or to where you can no longer move downward. The size of these steps is the Learning Rate.  Don’t forget as I show this this illustration that gradient decent is still about optimal weights to build modeling predictions.  Okay, back to the example, now that we have found the direction we need to nudge the weight, we need to find how much to adjust the weight.  This is where use the Learning Rate. This is referred to as a hyper-parameter or a value required by a model.  These values are “figured-out” either by trial and error or by building grid searches. There is no “one-size-fits-all” for hyper-parameters. I once heard in an education tutorial to think of the Learning Rate a “step in the right direction.”  The slower the learning rate the better but then it takes longer to figure-out the model.  

Next, is the Loss Functions (it’s also called the Cost Function) “how good” a model is at making predictions for a given set of parameters. We need this Cost Function because we want to minimize it.

**One of the really interesting and powerful parts of XGBoost is the boosting process.  **

Okay, let’s move away from the illustration of going down the mountain and back to machine learning with XGBoost.  One of the really interesting part of Boosting are that the learners are actually weak learners with a high bias.  The predictiveness is just a tad better than random guessing. Each of these weak learners contributes some vital information for predictions, causing boosting technique to producing strong learners effectively combining these weak learners. The final strong learners brings down both bias and variance.

**Summary**

XGBoost is an ensemble method that is trying to create a predictions with “weak” learners.  Weak and strong refer to a measure of how correlated the learners are to target variable. The ensemble part of model is iteratively building models one after another so that the errors of the previous model are corrected by the next predictor until the training data is ready.  If you use Python, then import the libraries for XGBoost and include it with the other machine learning models to “see” it model result


