---
title: "Probability Estimation with SVM"
---

- [[SVM]] is a [[binary classification]] algorithm that identifies whether the computed value f(x) is positive or negative.
- It is not essentially a [[stochastic model]]. However, [[LIBSVM]] and [[sklearn]] implement stochastic inference. How does this work?

- [A Note on Platt’s Probabilistic Outputs for Support Vector Machines](https://www.csie.ntu.edu.tw/~cjlin/papers/plattprob.pdf)
- Platt(2000)
    - ![image](https://gyazo.com/2d12317f6e5d60ce9fe55a6ac142962a/thumb/1000)
    - The story is that there are often applications where people want to know the probability of a label rather than predict it, so Platt suggested that it would be a good idea to approximate it with a sigmoid.
- A, B are parameters, obtained by maximizing log-likelihood
    - In other words, it is equivalent to "learning [[logistic regression]] with the SVM output values as explanatory variables, rather than putting them into sign.
- 5-fold cross-validation
    - (Train SVM on 4/5 of the data, find f(x) for the remaining 1/5, and learn the relationship between f(x) and the correct answer using logistic regression).
- In cases such as when the SVM cleanly separates the two, the logistic regression is naturally a step function
    - So I'm applying smoothing, etc.

- Notes on using predict_proba in Scikit-Learn
    - Understand that "the algorithm that does not return probability values has logistic regression layered on top of it to make it return probability values."
    - Since SVM is trained 5 times on 4/5 data, well, it takes roughly 4-5 times longer.
    - Making the SVM return probability values does not increase the accuracy of the SVM's identification. That is not the purpose of the mechanism.
    - If the parameters are properly chosen, they will be of similar accuracy.

#Machine Learning

---
This page is auto-translated from [/nishio/SVMで確率推定](https://scrapbox.io/nishio/SVMで確率推定) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.