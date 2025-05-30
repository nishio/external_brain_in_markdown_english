---
title: "Minimum mathematical knowledge required for machine learning"
---

Q: What is the minimum mathematical knowledge required for [[machine learning]]?
A: I don't see why someone who simply uses a library would need mathematical knowledge.

Q: Don't say that...

So brainstorm what knowledge is needed for people who just use the library.
Move up what looks important.

scientific methodology
- Proper experimentation and observation of experimental results.
- If it is not disprovable, it is occult.
- I was able to identify them with 90% accuracy using the Deeper Plugin!"
    - We should check and compare more basic methods to see how accurate they are.
    - Using Deep Learning to achieve 90% accuracy on a problem where logistic regression gives a 92% system is just stupid.

[dimensional analysis](https://ja.wikipedia.org/wiki/%E6%AC%A1%E5%85%83%E8%A7%A3%E6%9E%90)
- Do not add different units.
- 70% plus 60 kg equals 130!" is no good.
- With a metaphor like this, you think, "You wouldn't do that, would you?"
- But there are a surprising number of people who do things like "add the number of pieces and the probability" without a hitch.

Explanatory and Objective Variables
- To talk about whether there is labeled data or not, we need to understand what labels are in the first place.

graph
- Graph reading is required.
- A histogram would be absolutely necessary.
- And scatter plots?
- Do you also have a box-and-whisker diagram?

Basic Statistics
- average
    - Mean, median, and mode are different.
- Variance and standard deviation
    - What is the probability of how many standard deviations and how much
- What happens to the variance when the amount of data doubles?

[scale level](https://ja.wikipedia.org/wiki/%E5%B0%BA%E5%BA%A6%E6%B0%B4%E6%BA%96)
- This could be bad if you don't know what you're doing.
- Don't feed nominal scale data to a library that wants interval scales, or something like that.

Concepts of space in more than 3 dimensions
- Some people think of vectors as arrows in a two-dimensional plane or in three-dimensional space, and when you get to four or more dimensions, they think, "Time axis?" Some people get like.

vector
- It's just a string of numbers!

matrix
- It's just a two-dimensional array!
- You don't do matrix operations or anything like that.

differential (e.g. calculus)
- A working person who is not good at math will not be able to do it after reading one lukewarm article.
- You can understand that and use the library instead of implementing it yourself, it's faster.
- If you want to implement a multilayer perceptron from scratch yourself, or if you want to know how a multilayer perceptron works, you need to learn.
- I would suggest reading a first year college calculus textbook or something like that.
    - Read a linear algebra textbook on matrices as well.

log rule

normal distribution

Curse of the dimension
- I want you to have a sense that a large dimensional space is a bad idea.
- But even if I don't have a sense of dimensionality, I feel like I could just say, "We need a lot of data."

probability
- Do we need it?
- I would need basic probability and Bayes rule to understand what's in the naive Bayesian.
- But there's something in the documentation about how to use it differently.
- > Like MultinomialNB, this classifier is suitable for discrete data. The difference is that while MultinomialNB works with occurrence counts, BernoulliNB is designed for binary/boolean features.

---
This page is auto-translated from [/nishio/機械学習で最低限必要な数学知識](https://scrapbox.io/nishio/機械学習で最低限必要な数学知識) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.