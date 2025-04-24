---
title: "antagonistic dimension"
---

![image](https://gyazo.com/188215f1b3ee60ca4f81903b19984082/thumb/1000)

antagonistic dimension
- 1: A and B are in conflict
- 2: (A+B) and C are in conflict
- 3: ((A+B)+C) and D are in conflict
    - Here the number of dimensions is not enough so that A and B become identical in the 2-dimensional [[PCA]].
    - Nonlinear dimensionality reduction ([[UMAP]], etc.) should split

Experiment.
py

```
A = np.array([-1, 0, 0])
B = np.array([1, 0, 0])
C = np.array([0, 2, 0])
D = np.array([0, 0, 4])
```

- ![image](https://gyazo.com/078d108b99832fb2e292de77e40571cb/thumb/1000)
- ![image](https://gyazo.com/01d4e366af768dca1b45154afc7f5809/thumb/1000)
    - SD=0.1
    - Lack of dimensionality causes A and B, which have the least separation in PCA, to mix and become one.
    - The UMAP is clearly divided
- ![image](https://gyazo.com/188215f1b3ee60ca4f81903b19984082/thumb/1000)
    - SD=0.5
    - They are also placed in close proximity in UMAP by A and B data becoming inseparable in the first place.
- ![image](https://gyazo.com/c733ac87a4d3201a55ddce0655e2ccdd/thumb/1000)
    - SD=0.75
    - A, B, and C cannot be separated and become connected.
- ![image](https://gyazo.com/4447528eb260a9cbdc596258b66831ca/thumb/1000)
    - SD=1
- ![image](https://gyazo.com/e1338356d66661eba164d7ef0c0201c5/thumb/1000)
    - SD=1.5
    - It's all in one piece.
    - [[string artifact]] is occurring.
    - Because of a lack of data?
    - You can't increase it by a factor of 10.
        - ![image](https://gyazo.com/f72964a477d766302cc989dad952a770/thumb/1000)

It looks like [[Variational Bayesian]] is needed to distinguish between them
- [Implemented EM algorithm for mixed Gaussian distribution in Numpy - Yasukazu Nishio's Hatena Diary](https://nishiohirokazu.hatenadiary.org/entry/20111108/1320724692)
- [Estimating clusters of mixed Gaussian distribution model by k-means method, EM algorithm and variational Bayesian respectively - Yasukazu Nishio's Hatena Diary](https://nishiohirokazu.hatenadiary.org/entry/20111122/1321925412)
- But it's not a good idea to assume a normal distribution for real data in the first place, so it's not a good idea.

---
This page is auto-translated from [/nishio/対立次元](https://scrapbox.io/nishio/対立次元) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.