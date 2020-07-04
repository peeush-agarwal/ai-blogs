---
title: Normal distribution
tags:
  - statistics
mathjax: true
prev_post: 
  title: Probability distributions
next_post: 
   title: Inferential statistics
---

+ A normal distribution curve is a type of probability distribution for continuous random variables.
+ Examples:
  + The distribution of height
  + The distribution of IQ
+ Properties of normally distributed curve are as follows:
  + It is symmetrical on both sides of its mean $$ \mu $$
  + The mean lies at the middle of the curve. `Mean = Median = Mode`
  + The total area under the curve is equal to `1` (since it is probability density function)
<!--more-->

+ Probability density function for Normal distribution is:  
  $$
  \begin{align*}
  & f(x) = \dfrac{e^{-\frac{(x-\mu)^2}{(2{\sigma}^2)}}}{\sigma \cdot \sqrt{2\pi}} \\
  & where, \\
  & \mu = mean \\
  & \sigma = \text{standard deviation} \\
  & e = 2.7
  \end{align*}
  $$

### 1-2-3 rule of normal distribution

+ The area of the curve lying within `1` standard deviation from the mean i.e between $$ \mu - \sigma $$ and $$ \mu + \sigma $$ is `0.68 or 68%`,
+ The probability of a continuous random variable that will lie within `1` standard deviation from mean is `0.68 or 68%`,
+ The probability of a continuous random variable that will lie within `2` standard deviation of the mean is `0.95 or 95%`,
+ The probability of a continuous random variable that will lie within `3` standard deviation of the mean is `0.997 or 99.7%`.
+ Graph for the same above:  
  ![1-2-3 rule of Normal distribution]({{ site.baseurl }}{% link assets/images/probability_dist/normal_dist_1_2_3_rule.png %})

### Standardized Normal distribution and Z-score

+ __Standardized Normal distribution__ is a special type of Normal distibution where $$ \mu = 0 $$ and $$ \sigma = 1 $$.
+ The standardized normal distribution is used to compare between differnt normal distributions.
+ A _normal distribution_ can be converted into _standardized normal distribution_ with the help of __Z-score__.
+ $$ \text{Z-score} = \dfrac{x - \mu}{\sigma} $$
+ For example, for a normal distribution with μ= 35 and σ = 5, the normal distribution curve and the standard normal distribution curve will look like this:
  ![Normal distribution vs Z-score]({{ site.baseurl }}{% link assets/images/probability_dist/compare_normal_and_z_score_plots.png %})
+ Z-score can be used to:
  + Calculate the probability of the occurence of a particular random variable  
    It is done with the help of [Z-table](http://www.youtube.com/watch?v=Oyjp6Ke8V9I&t=98s). Excel can also be used with function `NORMDIST`.
  + Compare normal distributions  
    __Example:__ Suppose that the marks obtained by the students of a class are normally distributed.
    + In the mid-term exam, the mean score was 50 out of 100, and the standard deviation was 10;
    + And in the end-term, the mean score was 60, and the standard deviation was 20.

    A student Ram scored 70 in the mid-term exam and 72 in the end-term exam. In which exam was his relative performance better?  
    __Soln:__ To answer above question, we can use Z-score to compare scores.
    + Z-score for Mid-term = (70 - 50)/10 = 2  
    + Z-score for End-term = (72 - 60)/20 = 0.6

    Looking at the Z-scores, we can conclude that Ram's relative performance was better in the mid-term exam compared to end-term exam.
