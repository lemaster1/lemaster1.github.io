---
layout: post
title:      "Naive Bayes Classification"
date:       2020-03-31 00:04:06 +0000
permalink:  naive_bayes_classification
---


The goals of this blog are below to provide below about Naive Bayes, specifically:

* Provide an overview and how to works for the Naive Bayes algorithm for classification.
* Advantages & disadvantages of Naive Bayes classification.

**Overview**

Naive Bayes algorithm is a method set of probabilities. For each attribute from each class set, it uses probability to make predictions. This algorithm falls under a supervised machine learning approach. I am trying to have as little math formulas as part of my explanations within my blogs.  I do this because as a data science professional I want to be able to explain model predictions without drawing drawing a bunch of calculations on a whiteboard.  In addition, I tend to understand concepts better when I try to explain them in everyday language.  I am, however, going to show “the math” behind Bayes theorem because I think that it’s helpful to understanding it before we “jump into” Naive Bayes algorithm for classifications.  I cut and pasted this below from Pathmind as well as writing a summary from it because I really like their explanations:

How to read notation:
* P(A) means “the probability that A is true.”
* P(A|B) means “the probability that A is true given that B is true.”
B is the basketball shot and A is the probability that the shot is made.  

The “cool” aspect of Bayes theorem is using the probability of one thing to predict the probability of another thing. It’s like a machine that cranks out  improved predictions as new data becomes available (or added to the model).  Bayes’ rule is updating the probability of an event as the observations or data is subsequently added.  If the data support the hypothesis then the probability goes up, if it does not match, then probability goes down.

**How it Works**

Why is naive added or part of the title to Naive Bayes Classification?  It’s naive because there’s an assumption made that the data features are independent of each other. This is naive because it’s almost never applicable in real world datasets.  

So how does it work?  Naive Bayes is classifier algorithm which uses the Bayes Theorem given some data features put them into class.   It predicts class membership probabilities for each class.   The class with the highest probability is considered as the most likely class. This is also known as Maximum A Posteriori (MAP).  Simple 1 feature example of the steps are below:

Step 1: Calculate the prior probability for given class labels
Step 2: Find Likelihood probability with each attribute for each class
Step 3: Put these value in Bayes Formula and calculate posterior probability.
Step 4: See which class has a higher probability.

**Advantages & Disadvantages**

Advantages
* Models are easy to build.
* Works well with very large data sets.
* Both binary and multiclass classification. 
* Provides different types of Naive Bayes Algorithms like GaussianNB, MultinomialNB, BernoulliNB.
* Works well with small training data


Disadvantages
* The model cannot learn relationship between features because it considers all the features unrelated.
* Issues with categorical values in test data model will assign a zero probability and will be unable to make a prediction. This is often known as Zero Frequency. To solve this issue use a smoothing technique such as Laplace estimation.

If there's not the difficulty of the two major disadvtages listed above, then this can be a realiable and fast preditive model tool to have ready for when you can use it.  I tend to rush to random forest and XGBoost right away.  I guess I "kinda" forget about this model becuase it was one of the first ones that I learned about.  I am going to build a function using scikit learn and run this model as well as the others that I like as well.  

Please let me know your thoughts about Naive Bayes Classifier 
