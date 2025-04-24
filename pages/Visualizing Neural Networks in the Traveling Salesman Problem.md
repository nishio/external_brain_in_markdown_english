---
title: "Visualizing Neural Networks in the Traveling Salesman Problem"
---

- A story about solving [[visualization (data, results, etc.)]] of [[neural net]] weights by attributing them to [[TSP]].

This is a visualization of the weights of the projection from the 8-dimensional input layer to the 32-dimensional intermediate layer of the [[multilayer perceptron]]. It looks like there is some structure. However, it is difficult to understand. To begin with, the horizontal axis is the IDs of the intermediate layers, and the IDs of the intermediate layers are not meaningful in order, because we are looking at shuffled ones. We want to observe this by "rearranging them so that similar ones are adjacent to each other". It can be attributed to the traveling salesman problem.
![image](https://gyazo.com/25d2a25ab29333331cc6e1e9d021cac4/thumb/1000)
So here is what I sorted. You can see that the middle tier is divided into halves and only half of the input is focused on.
![image](https://gyazo.com/34f4742106426e7ad3fdaf0684bfb5d7/thumb/1000)

python

```
from matplotlib import pyplot as plt
from ortoolpy import tsp
M = m.coefs_[0]
N = M.shape[1]
dist = {(i, j): np.linalg.norm(M[:, i] - M[:, j])
        for i in range(N)
        for j in range(N)
        if i != j}
_, result = tsp(range(N), dist)
plt.imshow(M[:,	result])
plt.show()
```


The other day, in a talk by the author of [Mathematical Optimization for Problem Solving - Qiita](https://qiita.com/SaitoTsutomu/items/8e062cdabd1ab8dab5ce), he introduced an example of using the traveling salesman problem to reorder and restore shredded images so that adjacent ones are as similar as possible. I came up with this application because the author introduced an example of restoring shredded images by rearranging them using the traveling salesman problem so that adjacent images are as similar as possible.
---
This page is auto-translated from [/nishio/巡回セールスマン問題でニューラルネットの可視化](https://scrapbox.io/nishio/巡回セールスマン問題でニューラルネットの可視化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.