---
title: "naïve Bayes"
---

Objective.
- Brief description of Naive Bayes
- Explain the difference between GaussianNB and BernoulliNB

Explain with spam filter
What we want to do:.
- S: Whether the email is spam or not
    - Binary classification to determine
For simplicity, only two pieces of information can be used: 1.
- A: "Whether the email contains the word A."
- B: "Whether the email contains the word B."

What we want to do:.
From the information in A and B, determine whether S=0 or S=1."
In the language of probability, it is expressed in terms of
Given A and B, find the conditional probability of S."
- $P(S|A,B)$
This is, for example, an abbreviation for "the probability that A appears and is spam when B does not appear" $P(S=1|A=1,B=0)$.

How do we seek this?
Using Bayes' theorem, the following equality holds.
- $P(S|A,B) = \frac{P(S)P(A,B|S)}{P(A,B)}$
In other words, from past emails.
- Probability of being spam $P(S)$.
- Probability that A and B are, for example, A=1, B=0 when they are spam $P(A, B|S)$.
- Probability that A and B are, for example, A=1, B=0 $P(A, B)$.
You can look up the Simply count the number of occurrences and divide by the total.

So far just Bayes.
So far, there were only two types of words, A and B.
In general, there are many words. Suppose there are 100 words $P(A_1, A_2, ... , A_{100}|S)$ has $2^{100}$ different values. Well, that's impossible.
Then, $P(A_1, A_2, ..., A_{100}|S) , A_{100}|S)$ is approximated by $P(A_1|S)\times P(A_2|S)\times ... \times P(A_{100}|S)$ is approximated by [$ P(A_1|S)\times P(A_2|S)\times ...
- This means that the assumption "the probability of occurrence of A1 is independent of the probability of occurrence of A2 under the condition of being spam" (conditional independence).
Approximating in this way, instead of calculating $2^{100}$ streets, you can just calculate 100 streets and multiply them to get a decent calculation.

Relationship to [tf-idf
$P(A_1|S)$ was "the probability that the word A1 appears in a sentence that is spam.
tf is "the number of times the word A1 appears in a sentence that is spam. If you add up the weights of A1 and A1, and divide by the total number of documents, you get $P(A_1|S)$.
$P(A_1)$ was "the probability of the word A1 appearing in any given sentence.
[[idf]] is the "reciprocal of the number of times the word A1 appears in all sentences. This can be similarly added together with binary weighting and divided by the total number of documents to get $P(A_1)$.
Since it appears in the numerator and denominator of Bayes' rule, "divide by the total number of documents" is a constant multiple, so it is approximately divided and disappears.


Difference between BernoulliNB and GaussianNB
$P(A_1|S)$
The difference is in what form the probability distribution is called.
In this example, it was a distribution that takes 0/1 values for "appears or does not appear" because it was the occurrence or non-occurrence of the word in the spam mail. Since this is a Bernoulli distribution, it is natural to use BernoulliNB.
For example, if you want to identify whether a mushroom is poisonous or not, the explanatory variables may take continuous values such as "the size of the umbrella when it is poisonous" and "the redness of the umbrella when it is poisonous. In such cases, GaussianNB assumes that these values will follow a normal distribution, which can be transformed to 0/1 with an appropriate threshold value and treated as a Bernoulli distribution. In such a case, it is called BernoulliNB.

#Machine Learning
---
This page is auto-translated from [/nishio/ナイーブベイズ](https://scrapbox.io/nishio/ナイーブベイズ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.