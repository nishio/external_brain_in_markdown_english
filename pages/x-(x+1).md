---
title: "x/(x+1)"
---

For estimating the probability p such that [$ p = x/(x+c)
To simplify the story, let c=1.
- Even if it is not 1, just divide both x and c by c and call them x and 1, respectively.

$p = x/(x+1)$
Since the value range of x is [0, infty), this can be regarded as y being (-infty, infty) mapped by x=exp(y)
- In the space of logarithms, dividing by c is just a log(c) parallel, so I brought c to the origin to simplify the discussion

- The definition of [[logistic]] [[sigmoid]] is
$\sigma(s) = 1 / (1 + \exp(-s))$
therefore
$\sigma(y) = 1 / (1 + \exp(-y))= \exp(y) / (\exp(y) + \exp(-y)\exp(y)) = x / (x + 1)$
In other words, $x/(x+1)$ corresponds to a probability estimate in the sigmoid.


![image](https://gyazo.com/eac341e8d11d062e3db5091a409083d1/thumb/1000)
- The distribution function $p(y<Y)$ in the figure is a mistake for [$ p(Y<y)
- When a random variable Y has a certain bell-shaped distribution in the space of y, its [[cumulative distribution function]] becomes an S-curve
- I want to find the parameters of the probability distribution by fitting this S-curve
    - Approach to do with logistic sigmoid
    - Approach using a bell-shaped distribution as a normal distribution and its S-shaped density function
- Estimating probabilities in x/(x+c) corresponds to the approach using the logistic sigmoid
        - [[logistic regression]]

What a joy to be attributed to sigmoid
- The sigmoid is commonly used to map -infty~infty values to probability values in various probability estimation models.
- For example, logistic regression does probability estimation by inner-producting a vector of weights on an input vector and plugging the resulting -infty~infty values into a sigmoid
- So when I heard that you were doing probability estimation with the formula "~," I thought, "Isn't that a special case of a known probability estimation model?
- What is exciting about the sigmoid is that it corresponds to logistic regression and neural networks that output probability values, so the "weight" parameters that are currently determined by feeling can be adjusted by training with appropriate teacher data.
- If it is important to increase the accuracy of the inference model, we can take that approach, and if it is not important, or if there is no data, we can keep the current decision-making approach, and we can increase the number of options.

relevance
    - [[Relationship between sigmoid and softmax]]


-----
Approach that was not good enough
[odds ratio - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%AA%E3%83%83%E3%82%BA%E6%AF%94)
$q/(1 − q)$
The value range is [0, infty)
$x = q/(1 − q)$
if we take ...
$y = \log(q) - \log(1-q)$


If the number of occurrences of a word is x and the number of occurrences of all words is $S = \sum x$, then the frequency of occurrence is x/S in a naive way.
That would mean that words that did not appear in the training data would have a frequency of 0, so add 1 to the denominator.
Frequency of known words is $x/(S+1)$ and frequency of unknown words is [$ 1/(S+1)
In the special case where there is only one kind of word $S = \sum x = x$, so
The frequency of occurrence of the word after smoothing is $x/(x+1)$.
In the so-called additive smoothing, this is further modified to
Frequency of known words is $(x + 1) /(S+c)$ and frequency of unknown words is [$ 1 /(S+c)
where c is the vocabulary number + 1


---
This page is auto-translated from [/nishio/x/(x+1)](https://scrapbox.io/nishio/x/(x+1)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.