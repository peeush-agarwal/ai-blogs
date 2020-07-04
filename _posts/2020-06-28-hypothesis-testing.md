---
title: Hypothesis testing
tags:
  - statistics
  - hypothesis-testing
category: 'Statistics and probability'
mathjax: true
prev_post: 
  title: Inferential statistics
next_post: 
   title: T-Test
---

+ An assumption or claim made about the entire population using the sample statistics after an analysis is performed on a sample is called __Hypothesis__.
+ What hypothesis testing helps you do is statistically verify whether a claim is likely to be true or not for the whole population.  
+ Thus, we can say that __Hypothesis testing is a method or procedure that tests the statistical validity of a claim.__
+ Components involved in Hypothesis testing:
  + __Null hypothesis $$ H_0 $$__: It states that there is no change or no difference in the situation and assumes that the status quo is true. It always has the `=` sign and it is a common belief about the population.
  + __Alternative hypothesis $$ H_1 $$__: It is the claim that opposes null hpothesis. It challenges the status quo and may or may not be proved. It never has the `=` sign and always challenges the status quo.
<!--more-->

+ Example: Jeep, a well-known car maker, claims that it car 'Compass' gives a mileage of at least 17 km/litre.
  + The null hypothesis for this case would be:  
    $$ H_0: \mu \geq 17 $$
  + The alternative hypothesis is:  
    $$ H_1: \mu < 17 $$

## Steps of Hypothesis testing

+ Step 1: Defining the hypothesis
  + State `null` and `alternative` hypothesis for the problem.
+ Step 2: Identify the associated distribution
  + Condition 1: `n > 30`, which means that the population sample size should be greater than 30 observations.
  + Condition 2: $$ \sigma $$ is known i.e. the population standard deviation is known.
  + If both of above conditions are satisfied, you go for a __normal distribution__ or __Z-test__; otherwise, you use the __T-test__.
+ Step 3: Determine the test statistic.
  + This is a value that is to be calculated from some given data, which is then used to compare the results arrived at with the tabular values.
  + The test statistic for a normal distribution or Z-test is defined as $$ Z = \dfrac{\overline{x} - \mu}{\frac{\sigma}{\sqrt{n}}} $$.
  + Here,
    + $$ \overline{x} $$ is the process mean,
    + $$ \mu $$ is the population mean,
    + $$ \sigma $$ is the standard deviation,
    + `n` is the sample size.
+ [Refer here](https://sphweb.bumc.bu.edu/otlt/MPH-Modules/BS/BS704_HypothesisTest-Means-Proportions/BS704_HypothesisTest-Means-Proportions3.html)
+ Example: Google claims that its internet browser 'Chrome' is the best in the industry as it has an optimum boot time of only 250 ms, with a standard deviation of 9 ms. Sam, a tech geek, wanted to test the claim of Google. So, he randomly collected boot time data of 165 devices of Chrome and got a sample mean of 247 ms.
  + Step 1: Define Hypothesis
    + $$ H_0: \mu = 250ms $$
    + $$ H_1: \mu \neq 250ms $$
  + Step 2: Conditions
    + Condition 1: n > 30. Here `n = 165` which is greater than 30.
    + Condition 2: $$ \sigma $$ is defined. Here $$ \sigma = 9ms $$
  + As we have both conditions satisified, it can be considered as Normal distribution. Z-test can be performed.
  + $$ Z-score = \dfrac{247 - 250}{\frac{9}{\sqrt{165}}} = -4.3 $$
  + If we test our hypothesis at 95% confidence level. For 95% confidence interval, $$ \text{Z critical values} = \pm1.96 $$. The test statistic value we calculated = -4.3
  + The region between -1.96 and + 1.96 is called __acceptance region__ and the region outside it is called __critical region__.
+ If the calculated Z-statistic is in the region of acceptance, you fail to reject the null hypothesis. If the calculated Z-statistic lies outside the region of acceptance, i.e in the critical region, you reject the null hypothesis.
+ The critical region depends upon the nature of the alternate hypothesis. An alternate hypothesis can be of two types:  
  1. Non-directional  
  When you test any non-directional hypothesis, you need to define the critical region on both the sides as you need to check whether the sample mean lies to left or right of the assumed population mean.  
  This kind of a test is called a __two-tailed test__ because you have to check both the tails of the sampling distribution.
  2. Directional  
  It will hypothesise that the population mean lies in a particular direction from the assumed mean. Such an alternative hypothesis is called a directional hypothesis.
     + Lower-tailed test  
     The critical region that lies on the left tail of the sampling distribution. Thus, the hypothesis test is called a one-tailed test, and more specifically, a lower-tailed test.
     + Upper-tailed test  
     The critical region that lies on the right tail of the sampling distribution. Thus, the hypothesis test is called a one-tailed test, and more specifically, an upper-tailed test.

## Errors in Hypothesis testing

It has 2 types of errors:

+ Type 1 error
+ Type 2 error

_ | $$ H_0 $$ True | $$ H_1 $$ True
--- | --- | ---
__Reject $$ H_0 $$__ | Type 1 error | None
__Fail to reject $$ H_0 $$__ | None | Type 2 error

### Type 1 error

+ This is where a good hypothesis is rejected.
+ $$ H_0 $$ is True, but it is rejected.
+ It is also called the __consumer's loss__ because it results in the consumer discarding a perfectly good material/service, causing his organisation a loss of time as well as monetary resources
+ Type 1 error is equal to __$$ \alpha $$, the level of significance.__

### Type 2 error

+ This is where a false hypothesis is accepted.
+ $$ H_0 $$ is False, but it is accepted.
+ It is also called the __producer's gain__ as it results in a faulty batch being produced by them to be accepted by a customer.
+ Type 2 error is denoted by __$$ \beta $$__, where (1 - $$ \beta $$) is also caleed the __power of the statistical test__.
