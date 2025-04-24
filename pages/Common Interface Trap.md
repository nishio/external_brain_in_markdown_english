---
title: "Common Interface Trap"
---

- There are several different
- Think about [[collaborating]] on these operations
        - Thinking about adding [Common Interfaces
    - Each separately [[Cost to learn]] is a waste of money.
- Different plurals have different areas of expertise.
- Ideally, both sides should be able to take advantage, but often both sides only have [[common areas]] and [[lose one's strength]].
![image](https://gyazo.com/ab259ca763419224b870fdc26f48f9c4/thumb/1000)

If A has a function that B does not
- Route 1: Unsupported routes
    - Implementation is easy
    - It's the unfortunate thing I wrote above.
- Route 2: Route to error
    - For example, a design that has an interface but causes an error when executed
    - In the end, the user must understand "what is available on which backend".
- Line 3: The line that you do your best to implement
    - Example: The [[machine learning]] library Scikit-Learn provides a [[Common Interface]] for different learning models.
        - For model m, method `m.predict_proba` returns the result of probability estimation
        - This method is also grown for SVMs that do not have the capability of probability estimation
        - Running SVM 5 times [[logistic regression]] on 4/5 data: [[Probability Estimation with SVM]].
    - Very labor intensive.
    - Not always possible to implement.
        - In that case, it is attributed to route 2.

- [[snare]] in [[Common Interface]]
#Software Design
#Design
---
This page is auto-translated from [/nishio/共通インターフェイスの罠](https://scrapbox.io/nishio/共通インターフェイスの罠) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.