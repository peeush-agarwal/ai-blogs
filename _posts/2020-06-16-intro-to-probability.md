---
title: Introduction to probability
tags:
  - statistics
mathjax: true
# prev_post: 
#   url: 2020-06-13-image-classification-opencv.md
#   title: Image classification using OpenCV
next_post: 
  url: 2020-06-18-joint-and-cond-probability.md
  title: Joint and conditional probabilities
---

### Definition

+ Probability is the measurement of the likelihood of the occurence of an event.
+ It ranges between 0 and 1.
+ `0` = impossible event.
+ `1` = certain event.

<!--more-->

### Terminology

1. Trial or experiment
   + An action whose result is uncertain.
   + Ex: toss of a coin, rolling a dice
2. Event
   + Single result of an experiment.
3. Sample space
   + Total number of possible outcomes of an experiment.
4. Sample point
   + One of the possible outcomes.

### Formula

$$ probability = \frac{\text{ No. of favorable outcomes}}{\text{ Total number of possible outcomes}} $$

__Important points to remember:__

+ Tossing a coin
  + Possible outcomes: `H`, `T` _(2 in total)_
  + Probability of getting either `H` or `T` is equal to $$ \dfrac{1}{2} $$
+ Throwing/Rolling a dice
  + Possible outcomes: `1`, `2`, `3`, `4`, `5`, `6` _(6 in total)_
  + Probability of the occurence of any number is $$ \dfrac{1}{6} $$
+ Pick a card from deck of cards
  + Possible outcomes: _(52 in total)_
    + `13` cards of hearts
    + `13` cards of spades
    + `13` cards of clubs
    + `13` cards of diamonds

### Steps to find the probability

1. List every possible outcomes of the experiment being performed.
2. Count every possible outcome of the experiment.
3. Count all the favourable outcomes.
4. Use the probability formula to determine the probability of the occurence of an event.