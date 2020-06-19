---
title: Probability distributions
tags:
  - statistics
mathjax: true
prev_post: 
  url: 2020-06-18-joint-and-cond-probability.md
  title: Joint and conditional probabilities
# next_post: 
#   url: 2020-06-01-deep-learning-with-opencv.md
#   title: Deep Learning with OpenCV
---

## Random variable

+ A variable that can produce possible values those are outcomes of a random experiment is called __random variable__.
+ Types:
  + __Discrete random variable__ is a random variable that has countable number of possible values.
    + Example: Random variable representing the sum of 2 dices.
  + __Continuous random variable__ is a random variable where the data can be infinitely random.
    + Example: Random variable representing the height of students in a class.

## Probability distribution

+ It is a table of values that shows the probabilities of all possible values of a random variable.
+ Probability distribution for _discrete_ and _continuous_ are different.

<!--more-->

### Example

+ Let's take an example of rolling 2 dices simultaneously.
+ Let X be a random variable representing the sum of 2 dices.
+ All the possible values of X are `2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12`
+ Let's tabulate the probabilities for all possible values of X:
  
  __X__ | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12
  :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---:
  __P(X)__ | $$ \dfrac{1}{36} $$ | $$ \dfrac{2}{36} $$ | $$ \dfrac{3}{36} $$ | $$ \dfrac{4}{36} $$ | $$ \dfrac{5}{36} $$ | $$ \dfrac{6}{36} $$ | $$ \dfrac{5}{36} $$ | $$ \dfrac{4}{36} $$ | $$ \dfrac{3}{36} $$ | $$ \dfrac{2}{36} $$ | $$ \dfrac{1}{36} $$

+ Probability distribution
  
  ![]({{ site.baseurl }}{% link assets/images/probability_dist/discrete_prob_dist.png %})

  The chart above is the probability distribution of a discrete random variable. In this case, the discrete random variable (X) is the sum of two dice.

### Probability mass function

A function, say, P is said to be a __probability mass function__ for a _random discrete variable_ X when P(X) gives the value of the probability of X. In the example above, P(2) is equal to `1/36`, where P is the probability mass function of the discrete random variable X, which is the sum of two dice.
