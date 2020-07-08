---
title: Practice questions
permalink: /:categories/:title.html
layout: defaults/q-and-a
tags:
  - statistics
  - practice-questions
category: 'Statistics and probability'
mathjax: true
prev_post: 
  title: F-Test
# next_post: 
#    title: 
---

## What is the difference between univariate, bivariate and multivariate analyses?

+ **Univariate analysis**: The data which is being analysed contains one variable. For example, analysing the customers visiting an e-commerce fashion website. The data can be divided into men, women and kids, as following:  
  
  Category | Number per hour
  --- | ---
  Women | 78
  Men | 49
  Kids | 12

  The major purpose of this analysis is to describe and find patterns in data.
+ **Bivariate analysis**: It is used to find relationships between two different variables. For example, finding the relationship between Employee satisfaction level and income.
+ **Multivariate analysis**: It is the analysis of three or more variables. For example, analyse the factors that could have affected the lower sales of a newly launched product.

## Explain the power of statistical tests?

The power of a statistical test is inversely proportional to the probability of making a Type-2 error ($$ \beta $$); so, it is equal to $$ 1 - \beta $$. [More...]({{ site.baseurl }}{% link _posts/2020-06-28-hypothesis-testing.md %}#header1)

## What is the difference between cluster sampling and stratified random sampling?

+ In **stratified random sampling**, the whole population is divided into strata based on common characteristics. Then, certain elements are selected from each stratum.
+ On the other hand, in **cluster sampling**, the whole population is divided into clusters, and then some of the clusters are chosen randomly to create a sample.

[More...]({{ site.baseurl }}{% link _posts/2020-06-26-inferential-statistics.md %}#header1)

## What does the p-value signify and why is the p-value approach preferred over Z-test or T-test?

+ When you perform a statistical test a **p-value** helps you determine the significance of your results in relation to the null hypothesis.
+ The level of statistical significance is often expressed as a p-value between `0` and `1`. The smaller the p-value, the stronger the evidence that you should *reject the null hypothesis*.
+ The advantage of **p-value approach** is that you do not need to state the confidence level ahead of solving the hypothesis, as it becomes difficult to determine the confidence level in any particular situation.

[More...]({{ site.baseurl }}{% link _posts/2020-07-04-p-value.md %})

## In a dataset, the missing values are spread within 2 standard deviations of the mean. What percentage of data would remain unaffected?

Let’s assume that the data is normally distributed. In a normal distribution:

+ 68% of the data lies between **one** standard deviations
+ 95% of the data lies between **two** standard deviations, and
+ 99.7% of the data lies between **three** standard deviations

Therefore only 5% of the data will remain unaffected. [More...]({{ site.baseurl }}{% link _posts/2020-06-25-normal-distribution.md %}#header0)

## Explain the types of errors in hypothesis testing?

[Read from here]({{ site.baseurl }}{% link _posts/2020-06-28-hypothesis-testing.md %}#header1)

## What is the use of A/B testing?

Testing the alternate versions of websites is important in digital marketing, search engine optimisation etc. By testing the alternate versions of a website, A/B testing enables data-driven decision-making instead of making decisions based on simple gut feeling.
For example, an e-commerce company that sells multiple products on its website wanted to increase its sales on its website. To increase the sales, they used A/B testing. They changed the ‘Buy Now’ button to ‘Shop Now’, and this drove 17% more people to click on that button. This dealt a significant impact on the revenue of the company. So, this is an example of how a small change can produce significant results for a business and why A/B testing is very important. [More...]({{ site.baseurl }}{% link _posts/2020-07-04-a-b-testing.md %})

## When do we use the Z-test, T-test, Chi-square test, and F-test?

+ **Z-test**: It is used to test the hypothesis when the population data is normally distributed and the following conditions are met:
  + Condition 1: n > 30, which means that the population sample size should be greater than 30 observations
  + Condition 2: 𝝈 is known, i.e. the population standard deviation is known
+ **T-test**: It is used to test the hypothesis when the population data is normally distributed and the following conditions are met:
  + Condition 1: n < 30, which means that the population sample size should be less than 30 observations
  + Condition 2: 𝝈 is not known, i.e. the population standard deviation is unknown
+ **Chi-square test**: This test is used to determine if there is a significant relationship between two nominal (categorical) variables.
+ **F-test**: F-test is used to test the hypothesis on the equality of two population variances.

## What is the difference between Bernoulli distribution and binomial distribution?

[Read from here]({{ site.baseurl }}{% link _posts/2020-06-18-probability-distributions.md %}#header1)

## What is the difference between cluster sampling and systematic sampling?

+ In **cluster sampling**, the whole population is divided into clusters, and then some of the clusters are chosen randomly to create a sample.
+ Whereas in **systematic sampling**, a starting point is selected in the population, and then, the elements are selected at regular, fixed intervals to create a sample.

## What does a confidence interval of 95% signify?

A confidence interval of 95% signifies the range of values within which you can be 95% confident that the mean will lie in that range of values.

## What do you understand by normal distribution?

[Read from here]({{ site.baseurl }}{% link _posts/2020-06-25-normal-distribution.md %})

## What is a test statistic?

It is a value calculated from the sample data that is used to evaluate the strength of evidence in support of a null hypothesis.
For example, if the test statistic in a hypothesis test is equal to ‘A’ and the probability of observing the test statistic ‘A’ is less than the significance level, the null hypothesis is rejected.

## What is the difference between the mean value and the expected value?

+ **Mean** and **expected** values are the same but are used in different contexts.
+ We take the **mean value** in the context of probability distribution or samples,
+ and we take the **expected value** in the context of random variables.
