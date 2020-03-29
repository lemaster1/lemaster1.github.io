---
layout: post
title:      "Linear Regression Preprocessing Steps"
date:       2020-03-29 16:27:03 +0000
permalink:  linear_regression_preprocessing_steps
---

The goals of this blog are:

* Provide overview of linear regression.

* Steps taken during the the data scrubbing and data exploration stages of building linear regression models.  My hope is that this is a key objective for this blog is to have a resource where we can go for preprocessing data steps for linear regression.

* Advantage and disadvantages of of linear regression models.


**Overview**

A high-level definition of linear regression model.  It's a statistical model with relationship between a dependent variable (or the target) and either one or more independent variables.  If there’s more than one independent variable then need to do multiple regression models. A linear association is used to describe a straight-line relationship between a variable and a constant; where y is dependent upon X (so X is the independent variable).  A key goal of regression analysis is to isolate the relationship between each independent variable and the dependent variable.

Linear regression models require a decent amount of data prep before building them, unlike machine learning models like XGBoost, Random Forests as well others.  See below.   


**Steps for Preprocessing Data for Linear Regression Models**

* Remove missing & null values.  Probably will also want to look for and drop irrelevant observations too.

* Convert string data that are actually numbers into integers.

* Remove outliers.

* Remove multicollinearity.  I think of multicollinearity as different data that is redundant.  It predicts the same outcome even though it's different.  This happens when predictors in a regression are highly related so that it doesn’t provide independent information to the regression.

* The data should be normally distributed.  This is the bell curve that we are familiar with for some of classes where the teacher dulled out grades based upon how we performed together versus standard grading scale.   It’s a  distribution where most of the observations cluster around the central peak Extreme values move symmetrical to both ends of the tails of the curve.  

* Normal distribution is one of the most important parts of the preprocessing of the data.  There are many reasons why and an entire article could be written about the importance.  I’ll just note that if we want optimal estimators that are "unbiased of minimum variance", or maximum likelihood then we need normal distribution of our data.  Of course, in the “real-world” perfect normal distribution is not likely but still need to make the efforts to get it as close as possible to it.

* Should have little to no autocorrelation.   This happens when the residuals are not independent from each other.  In statistics, a residual refers to the amount of variability in a dependent variable that remains after the variability explained by the predictors.   A good example and common example given are stock prices, where the price is not independent from the previous price.  How about this simple equation:  residual = observed – predicted.  One last thing, while a scatterplot is a good visualization for autocorrelations something like a Durbin-Watson test should be used.  There are other tests as well.  

**Advantages**

* Easy to interpret and explain.  I think that linear regression are great at this because the models show us the “how and what” of our predictions that sometimes are not easy to find with other algorithms.  It’s “hard to beat” the simple interpretation of these models, especially within business because those stakeholders prefer to know the how of our predictions

* It’s great in business models where we want to chose one thing over the other; for example, whether to chose one marketing promotion versus another one.

* It seldom overfits because can use it can be easily avoided using some dimensionality reduction techniques, regularization (L1 and L2) techniques and cross-validation. Please see explanation for Ridge (L1) and Lasso (L2) by Jitesh Khurkhuriya within this Link:  https://www.quora.com/What-is-the-difference-between-L1-and-L2-regularization-How-does-it-solve-the-problem-of-overfitting-Which-regularizer-to-use-and-when. His explanations are incredible.

**Disadvantages**

* I guess that I am stating the obvious but its biggest limitation is the assumption of linearity between the dependent and independent variables.  It assumes  there’s a straight-line relationship between them. 

* As you can see from above there’s a decent amount of data preprocessing work that needs to be done before even starting to train the model.  Of course, Python has library methods your can use from Pandas, Matplotlib, scikit learn and to others to compete this phase faster and probably more accurate.  

* Sensitive to outliers and data noise.

I am hopeful that you found some value in this blog article.  Linear regression algorithms can be powerful tools when we can get the data to work and used in the scenarios where they preform well.  I did many linear regression models for my marketing tasks with most of my jobs because it controlled marketing budgets as well as finding the best competing variables.  

