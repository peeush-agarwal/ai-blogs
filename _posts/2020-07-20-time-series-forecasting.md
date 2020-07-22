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

### 2. Collect the data

It is very important because all your forecast is dependent on the data. There are three important characteristics that every time series data must exhibit in order for us to make a good forecast.

+ **Relevant:** The time-series data should be relevant for the set objective that we want to achieve.
+ **Accurate:** The data should be accurate in terms of capturing the timestamps and capturing the observation correctly.
+ **Long enough:** The data should be long enough to forecast. This is because it is important to identify all the patterns in the past and forecast which patterns repeat in the future.

There are the various types of data sources to get a time-series data, which are:

+ **Private enterprise data:** E.g. financial information about the quarterly results of any private organisation.
+ **Public data:** E.g. government publishes the economic indicators  such as GDP, consumer price index etc.
+ **System/Sensor data:** E.g. Logs generated by the servers during their 24/7 working hours.

### 3. Analyze the data

There are components associated with time series, which are:

+ Level: This is the baseline of a time series. This gives the baseline to which we add the different other components.
+ Trend: Over a longterm, this gives an indication of whether the time series moves lower or higher. For example, in the following Sensex graph you can clearly observe that with  time, the overall value is increasing i.e. this particular time series data has an increasing trend.

  ![Trend component example]({{ site.baseurl }}{% link assets/images/time_series_forecast/Trend_Component.png %})

+ Seasonality: It is a pattern in a time-series data that repeats itself after a given period of time. For example, in the following graph 'Monthly sales data of company X', you can clearly observe that a fixed pattern is repeating every year. The simplest example to explain this could be, say, the sales of winter wear in India. In winter, during months like November-January, you would expect these sales to be very high whereas for the other months, the sales might be low. This shows a seasonality pattern and proves to be very useful when making forecasts.

  ![Seasonal component example]({{ site.baseurl }}{% link assets/images/time_series_forecast/Seasonal_Component.png %})

+ Cyclicity: It is also a repeating pattern in data that repeats itself **aperiodically**. Read more about cyclicity [here](https://otexts.com/fpp2/tspatterns.html)

  ![Cyclicity component example]({{ site.baseurl }}{% link assets/images/time_series_forecast/Cyclicity_Component.png %})

+ Noise: Noise is the completely random fluctuation present in the data and we cannot use this component to forecast into the future. This is that component of the time series data that no one can explain and is completely random.

  ![Noise component example]({{ site.baseurl }}{% link assets/images/time_series_forecast/Noise_Component.png %})

*Note: Every time-series data has "Level" and "Noise" components compulsory, whereas other components are optional.*

#### Handling missing values in time-series data

1. **Mean imputation:** Imputing the missing values with the overall mean of the data.
   ![Mean imputation]({{ site.baseurl }}{% link assets/images/time_series_forecast/MeanImputation.png %})
2. **Last observation carried forward:** We impute the missing values with its previous value in the data.
   ![Last observation carried forward]({{ site.baseurl }}{% link assets/images/time_series_forecast/LastObsCarriedFwd.png %})
3. **Linear interpolation:** You draw a straight line joining the next and previous points of the missing values in the data.
   ![Linear interpolation]({{ site.baseurl }}{% link assets/images/time_series_forecast/LinearInterpolation.png %})
4. **Seasonal + Linear interpolation:** This method is best applicable for the data with trend and seasonality. Here, the missing value is imputed with the average of the corresponding data point in the previous seasonal period and the next seasonal period of the missing value.
   ![Seasonal and Linear interpolation]({{ site.baseurl }}{% link assets/images/time_series_forecast/Seasonal+LinearInterpolation.png %})

#### Handling outliers in time-series data

Outliers are the data points within time-series which are way-off than expected data points. These may occur due to false readings or rare event.

We can detect and treat outliers in the time-series with following methods:

1. **Extreme value analysis:** Remove smallest and largest values in the dataset.
   ![Smallest and Largest values]({{ site.baseurl }}{% link assets/images/time_series_forecast/Outliers_Smallest_Largest.png %})
2. **Box plot:** The points lying on either side of whiskers are considered to be outliers. The length of whiskers can be defined by us according to the problem.
   ![BoxPlot]({{ site.baseurl }}{% link assets/images/time_series_forecast/Outliers_BoxPlot.png %})
3. **Histogram:** Simply plotting a histogram can also reveal the outliers - basically the extreme values with low frequencies visible in the plot.
   ![Histogram]({{ site.baseurl }}{% link assets/images/time_series_forecast/Outliers_Histogram.png %})

### 4. Model the data

Before modelling the data, time series need to be decomposed which can be done in two ways:

+ **Additive Seasonal Decomposition**
  When the magnitude of the seasonal pattern in the data does not directly correlate with the value of the series, the additive seasonal decomposition may be a better choice to split the time series so that the residual does not have any pattern.
+ **Multiplicative Seasonal Decomposition**
  When the magnitude of the seasonal pattern in the data increases with an increase in data values and decreases with a decrease in the data values, the multiplicative seasonal decomposition may be a better choice.
