---
title: "Normalization and Standardization"
---

    - There was some discussion about the confusion caused by similar words like [[normalization (e.g. in floating-point representation system)]], [[scaling (e.g. in computer graphics)]], and [[standardization]], so I have organized them. I have organized them.
- Normalization is the process of transforming data according to some standard and unifying the scale.
    - For example, "The range in which the value changes from variable to variable is different and unwieldy, so let's convert them all to the range of `[0, 1]`."
    - We can call it scaling.
- What criteria are used is not defined by the term "normalization."
    - So, if you want to avoid misunderstandings, it is better to specify the criterion as "normalization so that the data falls within the range of `[0, 1]`".
- In English, it is normalize, but what constitutes normal is not always the same.
- In some industries, there's a local rule that when you just say normalization, it's normalization by a standard of ~.
    - When I say "normalize a vector," in many fields I mean "set the length to one" [Normalized Vector -- from Wolfram MathWorld](http://mathworld.wolfram.com/NormalizedVector.html).
    - When I say "normalize a relation," I mean make the relation NORMAL FORM see [Normalization of a relation - Wikipedia [https://ja.wikipedia.org/wiki/%E9%96%A2%E4%BF%82%E3%81%AE%E6%AD%A3%E8%A6%8F%E5%](https://ja.wikipedia.org/wiki/%E9%96%A2%E4%BF%82%E3%81%AE%E6%AD%A3%E8%A6%8F%E5%) 8C%96]

- Among the various methods of normalization, the act of "normalizing to have mean 0 and variance 1" is called "standardization".
- This is because the normal distribution with mean 0 and variance 1 is called the "standard normal distribution.
- The expression standardize is used, for example, in the following article
    - [Standardized Score -- from Wolfram MathWorld](http://mathworld.wolfram.com/StandardizedScore.html): score minus mean divided by standard deviation
    - [Standardized Moment -- from Wolfram MathWorld](http://mathworld.wolfram.com/StandardizedMoment.html) Moment of the value minus the mean divided by the standard deviation

#Machine Learning

---
This page is auto-translated from [/nishio/正規化と標準化](https://scrapbox.io/nishio/正規化と標準化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.