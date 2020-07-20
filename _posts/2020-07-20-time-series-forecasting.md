---
title: Time-series forecasting
tags:
  - machine-learning
  - forecasting
category: 'Machine Learning'
mathjax: true
# next_post: 
#   title: Joint probability and conditional probablity
---

## Forecasting

It is the technique to predict future data analysing historical data.

## Type of forecasting

Quantitative forecasting | Qualitative forecasting
--- | ---
Based on the data and any repeating historical patterns in the data. | This procedure is taken when data is not available and historical patterns do not repeat. This is based on expert decision.
Captures complex patterns which humans cannot identify. | May not capture complex patterns.
No bias | Bias
Eg. Time-series forecasting | Eg. Delphi method

<!--more-->

## Terminologies

+ **Time-series data**: The data that has a time-component involved in it is termed as a time-series data. For ex: the number of orders made on a food ordering app per day is a time-series data.
+ **Time-series analysis**: Analysis on the time-series data to find useful insights and patterns is termed as time-series analysis. For ex: In a food ordering app example, it might have the data for every day logged in per hour. They might notice that in this data, the number of orders is significantly higher in, say, the 1-2 PM time slot but is significantly lower in the 3-4 PM time slot. This information might be useful for them as they would then be able to estimate the number of delivery boys required at a particular time of the day. Hence, time series analysis is indispensable while working with any time series data.
+ **Time-series forecasting**: It is basically looking at the past data to make predictions into the future. Say that the food ordering app wants to predict the number of orders per day for the next month in order to plan the resources better. For this, they will look at tons of past data and use it in order to forecast accurately.

![Basic Project flow]({{ site.baseurl }}{% link assets/images/time_series_forecast/Project_Flow.png %})

+ **Goal:** A set of business objectives. For example, maximising revenue, maximising capital, etc.
+ **Plan:** A set of actions that a business takes to achieve the goal. In order to come up with a good plan, they need a forecast.
+ **Forecast:** Is the prediction of the future.

## Problem statement: Air Passenger Traffic Forecasting problem

An airline company has the data on the number of passengers that have travelled with them on a particular route for the past few years. Using this data, they want to see if *they can forecast the number of passengers for the next twelve months.*  
Making this forecast could be quite beneficial to the company as it would help them take some crucial decisions like:

+ What capacity aircraft should they use?
+ When should they fly?
+ How many air hostesses and pilots do they need?
+ How much food should they stock in their inventory?

## Basic steps involved in any forecasting

+ Define the problem
+ Collect the data
+ Analyze the data
+ Build and evaluate forecast model

### 1. Define the problem

This is a crucial step in any Time-series forecasting or for that matter any type of analysis. We have to define and understand the problem well because if analysts doesn't define the problem (or goal) then it can be difficult to analyse the final outcome. We can divide our process into following, or what to forecast?

+ Quantity: Unit of problem to be forecasted. For ex: no. of units to sell, maximum occupancy to achieve, etc.
+ Granularity: Scope of forecasting. For ex: analysis at store level, region level or city level, etc.
+ Frequency: How frequent forecasting needs to be done? For ex: Daily basis, weekly basis, monthly, etc.
+ Horizon: Is it Short-term, medium-term or long-term forecasting?

There are some caveats while performing Time-series forecasting:

+ **The Granularity rule:** The more aggregate your forecasts, more accurate you are in your predictions. It is because aggregate data has lesser variance and hence, less noise.
+ **The Frequency rule:** This rule tells you to keep updating your forecasts regularly to capture any new information that comes in.
+ **The Horizon rule:** When you have the horizon planned for large number of months in the future, then you are more likely to be more accurate in your earlier months forecasts as compared to the later months.

> Now that you have understood the steps in defining the problem, let's apply them to the air passenger traffic problem.
>
> + **Quantity:** Number of passengers
> + **Granularity:** Flights from city A to city B; i.e., flights for a particular route
> + **Frequency:** Monthly
> + **Horizon:** 1 year (12 months)
