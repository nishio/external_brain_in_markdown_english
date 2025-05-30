---
title: "Integral of probability"
---

I was reading [[Information-Geometric Optimization]] about probability p
$\int f(x)P(x)dx$ and how to write
I was confused about what you meant by the mixed writing of $\int f(x) P(dx)$.

Footnote 1 convinced me to write an explanation to confirm my understanding.
- > Throughout the text we do not distinguish a probability distribution 𝑃, seen as a measure, and its density with respect to some unspecified reference measure d𝑥, and so will write indifferently 𝑃(d𝑥) or 𝑃(𝑥)d𝑥. The measure-theoretic viewpoint allows for a unified treatment of the discrete and continuous case.

With discrete probability P, P(x) = 1/6 corresponds to point x, for example, "The probability that the dice roll is 1 is 1/6".
So P in this case is $X \to \mathbb{R}$ if the possible range of x is X.

On the other hand, for a random variable A that follows a continuous probability, e.g., a normal distribution N(m, 1), "the probability that A matches the mean m" is zero.
A value is determined for a range (a subset of X) as in "the probability that A falls within the range between a and b."
The following equation is well-known for the normal distribution
- ${\displaystyle {f(x) = \frac {1}{\sqrt {2\pi \sigma ^{2}}}}\;\exp \left(-{\frac {\left(x-\mu \right)^{2}}{2\sigma ^{2}}}\right)}$
This is the "[[probability density function]]," and the probability is not the value of this function, but the integral over a range.
- ${\displaystyle \operatorname {P} (a\leq A \leq b)=\int _{a}^{b}f(x)\,dx}$
In other words, P in this case is a function $2^X \to \mathbb{R}$ from subsets of X to real numbers. There are many other properties that are more convenient than just $2^X \to \mathbb{R}$, so we call them collectively "[[measurement]] (measure)". See [theory of measurement - Wikipedia](https://ja.wikipedia.org/wiki/%E6%B8%AC%E5%BA%A6%E8%AB%96)

This equation specifies a and b
- ${\displaystyle \operatorname {P} (a\leq A \leq b)=\int _{a}^{b}f(x)\,dx}$
This is what happens if you don't clearly state it.
- ${\displaystyle \operatorname {P} (dx)=\int f(x)\,dx}$

You have a function g(x) and you want to calculate its expected value under a probability distribution P,
If it were a breakup...
- $\sum_{x\in X} P(x)g(x)$
If it was consecutive
- $\int f(x)g(x) dx$
but the notation in the IGO paper makes no particular distinction between the two.
- $\int P(dx)g(x)$
and write
- $\int P(x)g(x)dx$
I mean, I would write "I'm sorry, I'm sorry.

---
This page is auto-translated from [/nishio/確率の積分](https://scrapbox.io/nishio/確率の積分) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.