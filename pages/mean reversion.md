---
title: "mean reversion"
---

> [[return (to)]] is a phenomenon originally found in biological data, the first of which was published by [[Francis Gorton]] in 1877 on seed weight. Gorton grew and compared seven pairs of sweet pea seeds (seed weight varied from pair to pair, but was kept the same within a pair) and found the following
>
>  The seed weight of the offspring generation follows a normal distribution, as does the parent generation, and there is a near linear relationship when the mean diameter of the offspring generation seed is plotted against the mean diameter of the parent (what is now called linear regression can be applied).
>  However, the average diameter of the offspring tends to be closer to the overall average diameter when compared to the diameter of the parent (regression).
>  He initially called the slope of this line "coefficient of reversion" (he considered it a biological phenomenon, like so-called ancestral return). Later, he discovered that this effect was not biological but the result of data handling, and changed the name to "coefficient of regression. This result attracted attention because it seemed to contradict the idea of evolution at the time that individuals with advantageous traits survive and leave offspring, and that these traits become more pronounced with each successive generation. In fact, the seed size was more a matter of chance than of heredity. He further studied the term "correlation co-relation" in 1888, and used the letter "r" for the constant (correlation coefficient) that represented it.
[https://ja.wikipedia.org/wiki/平均への回帰](https://ja.wikipedia.org/wiki/平均への回帰)

[Regression towards the mean](https://www-users.york.ac.uk/~mb55/talks/regmean.htm)

python

```
>>> x = np.random.normal(size=100000)
>>> t1 = np.random.normal(x, 0.3)
>>> t2 = np.random.normal(x, 0.3)
>>> t1[t1 < -1].mean()
-1.5580399900412445
>>> t2[t1 < -1].mean()
-1.4286087235202238
>>> x[t1 < -1].mean()
-1.4260924898041
>>> x[t1 < -1].shape
(16822,)
```

---
This page is auto-translated from [/nishio/平均回帰](https://scrapbox.io/nishio/平均回帰) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.