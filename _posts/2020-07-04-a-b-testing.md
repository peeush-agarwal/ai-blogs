---
title: A/B testing
tags:
  - statistics
  - hypothesis-testing
category: 'Statistics and probability'
mathjax: true
prev_post: 
  title: p-Value approach
# next_post: 
#    title: 
---

+ The process of testing original and alternate versions of a website is known as A/B testing
+ In this process, we employ data-driven decision making instead of just gut feeling for a change in website.
+ For a website, divide all the visitors to the platform into two categories
  + one experiencing control group A
  + the other experiencing variation B
  A/B testing is a tool in the hands of managers, which they can use to understand the user behavior in two competing scenarios. This helps them select the best way in which they can make the customers complete the activities the website wants them to.
+ A/B testing helps you find out what you could change in the current product to increase user conversion rate.
<!--more-->

There are six major steps involved in A/B testing:

+ **Data collection**:
  + First, you have quantitative data, such as web traffic.
  + Second is transactional data, which indicates how many successful checkouts were made.
  + Then, you have some qualitative data obtained from the selected group of test users who provide feedback on their experience of the website.
  Thus, a combination of both quantitative and qualitative data helps us formulate an A/B test.
+ **Identify goals**: Determine the goals using metrics, and then make the necessary modifications to achieve these goals. The goal could be as simple as clicking a button, or as critical as making a financial transaction.
+ **Generate hypothesis**: The second step in A/B testing is to form a hypothesis. The hypothesis can take the form of — ‘*if a variable, then a result, because of a rationale*’.  
  For example,
  + the null hypothesis for the Devault’s case will be $$ H_0 $$: changing the ‘Buy Now’ button to ‘Shop Now’ will not increase the number of clicks.
  + And the alternative hypothesis will be $$ H_1 $$: changing the ‘Buy Now’ button to ‘Shop Now’ will increase the number of clicks.
+ **Create versions**: Develop multiple versions of the web page, plan various designs  of the webpage based on the hypothesis.
+ **Run experiment**: Kick-start the experiment and allow the customers to take part in it. In this experiment, some of the users are randomly directed to the older version and some to the new version. Then, the performances of both the pages are compared. While running the experiment, you need to ensure that there is no bias among the distribution of visitors to both the web pages.
+ **Analyse the results**: After the experiment, analyse the results comprehensively and determine if the results from the two web pages are significantly different or not. Devault analysed its result and found that the ‘Shop Now’ button brought 17% more clicks.

![A/B testing process]({{ site.baseurl }}{% link assets/images/probability_dist/a_b_testing_process.png %})

A/B testing finds application in multiple domains, such as:

+ Digital marketing
+ Search engine optimization
+ Video on demand services, and so on
