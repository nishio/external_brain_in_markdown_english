---
title: "Subdifferentiation"
---

[[FOBOS]]
[On Optimization Methods Using Subdifferentiation (4) | Preferred Research](https://research.preferred.jp/2010/12/subgradient-optimization-4/)

> At the end of the last issue, I wrote that [[L1 regularization]] has a strong effect of reducing the nonzero elements of the parameters, but it is not calculable in the first place with [[SGD]] because it is non-differentiable at the position wi = 0. ...... But when you think about it, don't you think that you can take any appropriate value between -1 and 1 as the value of the derivative...? [[Subdifferentiation]] answers that question.
[On Optimization Methods Using Subdifferentiation (3) | Preferred Research](https://research.preferred.jp/2010/12/subgradient-optimization-3/)

>  In the case of [[L2 regularization]], the penalty is almost zero if the value of wi approaches zero, while in the case of L1 regularization, the penalty is zero only if the value is exactly zero. Therefore, L1 has more power to reduce the non-zero elements of the parameter vector. As written, L1 regularization looks better, but it is difficult to use general numerical optimization methods because [[Differentiation is impossible]] at 0. So, various studies were born to realize L1 regularization.
- [On Optimization Methods Using Subdifferentiation (2) | Preferred Research](https://research.preferred.jp/2010/11/subgradient-optimization-2/)

- [On optimization methods using the underdifferentiation (1) | Preferred Research](https://research.preferred.jp/2010/11/subgradient-optimization-1/)

[[Cumurative Penalty]]
- [On Optimization Methods Using Subdifferentiation (Complete) | Preferred Research](https://research.preferred.jp/2011/02/subgradient-optimization-5/)

Linear regression mixing L1 and L2 is called [ElasticNet
[http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html)

---
This page is auto-translated from [/nishio/劣微分](https://scrapbox.io/nishio/劣微分) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.