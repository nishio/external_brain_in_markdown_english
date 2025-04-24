---
title: "Orientalists are logistic regression and Westerners are decision trees."
---

![image](https://gyazo.com/65041f75b35b16a9903a8525291966c5/thumb/1000)
- [[Westerners looking at the trees, Orienters looking at the forest]]  p.161
Should the target in the figure be in group 1 or group 2?
Orientals tend to choose Group 1 and Westerners Group 2.

- The problem of [[familial resemblance]] is the similarity between a 4D vector and two sets of vectors see [[Vector similarity]].
Since each set is labeled and given in advance [[supervised learning]].
Represent petal, inflorescence, leaf, and stem features as (1, 1, 1, 1) targets
Group 1
- (1, 1, 1, 0)
- (1, 0, 1, 0)
- (1, 1, 0, 0)
- (0, 1, 1, 0)
Group 2
- (0, 0, 1, 1)
- (0, 0, 0, 1)
- (0, 1, 0, 1)
- (1, 0, 0, 1)
Let us call the axes (a, b, c, d), respectively
Western identification discards information other than the d-axis to identify
Oriental-type identification uses all axes.

- [[logistic regression]] would determine "group 1 with probability 55%".
python

```
import numpy as np
from sklearn.linear_model import LogisticRegression

X = np.array([

 (1, 1, 1, 0),
 (1, 0, 1, 0),
 (1, 1, 0, 0),
 (0, 1, 1, 0),

 (0, 0, 1, 1),
 (0, 0, 0, 1),
 (0, 1, 0, 1),
 (1, 0, 0, 1)])

Y = np.array([0, 0, 0, 0, 1, 1,	1, 1])

m = LogisticRegression()
m.fit(X, Y)
```


:

```
In [3]: m.coef_
Out[3]: array([[-0.47815958, -0.47815958, -0.47815958,  1.16980067]])

In [4]: m.intercept_
Out[4]: array([0.08158937])

In [5]: m.predict_proba([(1, 1, 1, 1)])
Out[5]: array([[0.54564474, 0.45435526]])
```


coef_ shows -0.48 (weakly suggesting group 1) with respect to the a, b, and c axes, and +1.17 (strongly suggesting group 2) with respect to the d axis.
Logistic regression adds them together, so the decision on the axes a, b, and c wins and makes the decision that the group is group 1 by a narrow margin.

- If it is [[decision tree]], it is 100% group 2.
python

```
from sklearn.tree import DecisionTreeClassifier
m = DecisionTreeClassifier()
m.fit(X, Y)
```


:

```
In [7]: m.predict_proba([(1, 1, 1, 1)])
Out[7]: array([[0., 1.]])
```

The reason is simple: the learning process looks for "which of the axes is the most neatly divisible" and naturally leads to the conclusion that "d is the best way to make a decision". In the identification phase, no axis other than d is looked at.

---
This page is auto-translated from [/nishio/東洋人はロジスティック回帰で西洋人は決定木](https://scrapbox.io/nishio/東洋人はロジスティック回帰で西洋人は決定木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.