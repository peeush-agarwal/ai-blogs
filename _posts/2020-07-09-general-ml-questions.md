---
title: General ML questions
permalink: /:categories/:title.html
layout: defaults/q-and-a
tags:
  - machine-learning
  - practice-questions
category: 'Machine Learning'
mathjax: true
# prev_post: 
#   title: A/B testing
# next_post: 
#    title: Practice questions
---

## What is Linear regression?

+ **Linear regression** is the machine learning(ML) algorithm which finds the best linear-fit relationship on any given data, between independent and dependent variables.
+ It is mostly done by the **Sum of Squared Residuals** method.
+ Sum of the residuals of a linear regression model is always zero.

## What are the assumptions in a Linear regression model?

1. **Assumption about the form of the model**:
   *Linearity assumption*: It is assumed that there is a linear relationship between the dependent and independent variables.
2. **Assumptions about the residuals**:
   a. *Normality assumption*: It is assumed that the error terms, $$ \epsilon_i $$ are normally distributed.
   b. *Zero mean assumption*: It is assumed that the residuals have a mean value of zero.
   c. *Constant variance assumption*:
      + It is assumed that the residuals have same (but unknown) variance i.e. $$ \sigma^2 $$.
      + This assumption is also known as the **assumption of homogenity** or **homoscedasticity**.
   d. *Independent error assumption*: It is assumed that the residuals are independent of each other i.e. their pair-wise covariance is zero.
3. **Assumptions about the estimators**:
   a. The independent variables are measured without error.
   b. The independent variables are independent of each other i.e. there is no multi-collinearity in the data.

## What is Feature engineering? How do you apply it in the process of modelling?

+ *Feature engineering* is the process of transforming raw data into features that better represent the underlying problem to the predictive models, resulting in improved model accuracy on unseen data.
+ In simple words, it is the development of new features that may help you to understand and model the problem in a better way.
+ Types of feature engineering:
  + Business-driven:
    + This revolves around the inclusion of features from a business point of view.
    + The job here is to transform the business variables into features of the problem.
  + Data-driven:
    + In this, the features you add do not have a significant physical interpretation, but they help the model in prediction of the target variable.
+ To apply feature engineering, one must be fully acquainted with the dataset.
  + This involves knowing *what the given data is*, *what it signifies*, *what the raw features are*, etc.
  + You must also have a crystal clear idea of the problem, such as *what factors affect the target variable*, *what the physical interpretation of the variable is*, etc.

## What is the use of regularisation? Explain L1 and L2 regularisation techniques?

+ *Regularisation* is the technique that is used to tackle the problem of overfitting of the model.
+ At times, the simple model might not be able to generalize the data and the complex model overfits. To address this problem, regularisation is used.
+ Regularisation is nothing but adding the coefficient terms ($$ \beta $$s) to the cost function so that the terms are penalised and are small in magnitude.
+ This essentially helps in capturing the trends in the data and at the same time prevents overfitting by not letting the model become too complex.
+ **L1 or LASSO regularisation**:
  + Here, the absolute values of the coefficients are added to the cost function.  
  + $$
  \begin{align*}
  \sum_{i=1}^n{(Y_i - \sum_{j=1}^p{x_{ij} \cdot \beta_j})^2} + \lambda \cdot \sum_{j=1}^p{|\beta_j|}
  \end{align*}
  $$
  + This regularisation technique gives sparse results, which leads to feature selection as well.
+ **L2 or Ridge regularisation**:
  + Here, the squares of the coefficients are added to the cost function.
  + $$
  \begin{align*}
  \sum_{i=1}^n{(Y_i - \sum_{j=1}^p{x_{ij} \cdot \beta_j})^2} + \lambda \cdot \sum_{j=1}^p{\beta_j^2}
  \end{align*}
  $$

## How to choose the value of the parameter Learning rate?

+ If the value is too small, the gradient descent algorithm takes ages to converge to the optimal solution.
+ On the other hand, if the value of the learning rate ($$ \alpha $$) is high, the gradient descent will overshoot the optimal solution and most likely never converge to the optimal solution.
+ To overcome this problem, you can try different values of alpha over a range of values and plot the cost vs the number of iterations. Then, based on the graphs, the value corresponding to the graph showing the rapid decrease can be chosen.
+ If you see that the cost is increasing with the number of iterations, then your learning rate parameter is high and it needs to be decreased.
