---
title: "distribution of text-embedded vectors"
---

What is the shape of the distribution of text embedding vectors in the first place?

Data is from 18129 data retrieved from X. Argument 7574 data extracted by Talk to the City extruction.
- This is embedded in a vector space of 3072 dimensions with `text-embedding-3-large

The embedding vectors returned by OpenAI are normalized so that all vectors have length 1
- So it is distributed on a sphere of 3072 dimensions.
py

```
def p(x):
   print(f"{x.mean()} ± {x.std() * 3}")

norm = np.linalg.norm(embeddings_array, axis=1)
p(norm)  # -> 0.999999999999999 ± 1.2314317043463034e-15
```


Values for each axis are clustered in a narrow range of about SD 0.01
py

```
axis_std = embeddings_array.std(axis=0)
pd.DataFrame(axis_std).describe()
```

![image](https://gyazo.com/ebb5576bf01e407dcd2ebb179200a737/thumb/1000)

Of the 3072 dimensions, 80 dimensions have 60% of the information.
- 90% of the information is scattered over 500 dimensions.
- ![image](https://gyazo.com/30c0213dba12ea74a72737bb6d841a71/thumb/1000)![image](https://gyazo.com/c8e43b1a3a004cd49867e7b23db9d529/thumb/1000)
- Very high dimensional, two dimensional, not even 10% of the information.

The inner product of each data with respect to the other data is about 0.1~0.7 with an average around 0.4
- ![image](https://gyazo.com/ada46b6a0db24a1bbcb7a9a3a9776aac/thumb/1000)
    - Histogram with order shuffled and inner product with neighboring vectors
- The values on each axis move in a narrow range of about SD 0.01, but the overall range is pretty wide...
    - Is this a sensory gap caused by the fact that the belt on the higher dimensional sphere is actually very wide?
        - [[Curse of the dimension]]
- If we keep the Euclidean distance, it looks like this
    - ![image](https://gyazo.com/a0f8e6ccf0ed0ae9132327c5cc716656/thumb/1000)
    - Most data are about 0.8~1.4 away from most other data.
    - This is a pretty important feature, because the default value of eps for DBSCAN is 0.5, which means that "almost all points are not adjacent".
        - > eps float, default=0.5
        - > The maximum distance between two samples for one to be considered as in the neighborhood of the other.
            - [DBSCAN — scikit-learn 1.7.dev0 documentation](https://scikit-learn.org/dev/modules/generated/sklearn.cluster.DBSCAN.html)

HDBSCAN condensed_tree_.plot
- Default HDBSCAN (min_cluster_size=5)
    - ![image](https://gyazo.com/81bdadbbdc05533e95a2e2fdfa45d98a/thumb/1000)
- Smoothed density estimated by HDBSCAN(min_cluster_size=30)
    - ![image](https://gyazo.com/aa714280b2b571514ae5304746851cbe/thumb/1000)
    - So, roughly speaking, it's "one big cluster with a little tiny bump on it."
    - In the "thin density is OK" area smaller than lambda 1.0, all 7000 pieces are connected to one another.
    - In the ~1.2 region, small sets that are not considered clusters leave the cluster, leaving only about 1000 clusters.
    - That small set is divided into three parts.
    - min_cluster_size=5, the number of small sets to be considered as clusters is increased and drawn more finely.

---
This page is auto-translated from [/nishio/テキスト埋め込みベクトルの分布](https://scrapbox.io/nishio/テキスト埋め込みベクトルの分布) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.