---
title: Joint probability and conditional probablity
tags:
  - statistics
  - probability-basics
category: 'Statistics and probability'
mathjax: true
prev_post: 
  title: Introduction to probability
next_post: 
  title: Probability distributions
---

## Joint probability

+ Joint probability is the probability of the occurence of 2 events simultaneously.
+ 2 events are independent of each other in Joint probability.
+ $$ P(A \cap B) = P(A) \cdot P(B) $$

<!--more-->

### Examples

__Ques.__ What is the probability of you getting an 8 and a red card while drawing a card from a deck?  
__Soln.__

$$
\begin{align*}
& P(8 \cap red) = P(8) \cdot P(red) \\
& P(8 \cap red) = \frac{4}{52} \cdot \frac{26}{52} = \frac{1}{26}
\end{align*}
$$

__Ques.__ A bag contains `3` red balls, `5` green balls, and `10` black balls. What is the probability of you getting either a red ball or a green ball when you randomly draw a ball from the bag?  
__Soln.__

$$
\begin{align*}
& P(red) = \frac{3}{18} \\
& P(green) = \frac{5}{18} \\
& P(\text{red or green}) = \frac{3}{18} + \frac{5}{18} = \frac{4}{9}
\end{align*}
$$

## Conditional probability

+ It is the probability of an event when some other event has already occurred.
+ In Conditional probability, `2` events are dependent on each other.
+ Notation: $$ P(B \vert A) $$, _read as Probability of B given that A has already occurred_

### Formula

$$ P(B \vert A) = \frac{P(B \cap A)}{P(A)} $$

### Examples

__Ques.__ In a game of cards, a player wins if he draws two cards from the same unit. If the first card is a spade, what is the probability that the player will win?  
__Soln.__ The probability of another spade from the deck would be $$ \dfrac{12}{51} $$. Since 1 spade has already been drawn from the deck as first event.

__Ques.__ A bag contains `4` red balls and `5` green balls. You draw a ball from it without replacing it with another one. What is the probability of you drawing a green ball in the second draw, provided that it was a red ball that you got in the first draw?  
__Soln.__ $$ \text{The probability of red ball} = \dfrac{4}{9} $$. Now the probability of ball being green in second draw $$= \dfrac{5}{8} $$.

## Baye's Theorem

This describes the probability of an event, based on prior knowledge of conditions that might be related to the event. If you know the Conditional probability $$ P(A \vert B) $$, you can use Baye's rule to find out the reverse probability $$ P(B \vert A) $$.

$$ P(A \vert B) = \frac{P(B \vert A) \cdot P(A)}{P(B)} $$

__Generic formula__

$$ P(A_i \vert B) = \frac{P(B \vert A_i) \cdot P(A_i)}{\sum_{i=1}^{n}P(B \vert A_i) \cdot P(A_i)} $$
