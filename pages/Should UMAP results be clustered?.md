---
title: "Should UMAP results be clustered?"
---

2024-11-08
When I was experimenting with [[clustering]] the resulting data from [[UMAP]] with [[DBSCAN]], I felt that the assumption in clustering that the data points should belong to some single cluster was undesirable.
- At the time of UMAP, high-dimensional data is already visualized with dimensionality reduced to two dimensions.
- Even if clustering is used to explain this, it is not necessary to "make all data points belong to one of the k clusters".
- You are making the problem more difficult by putting in constraints that are not necessary.
- I think you are lowering the quality of downstream [[cluster commentary by AI]] by doing unreasonable clustering.
- Instead, it may be better to extract a few "high-density clumps" and provide AI explanations for them, which would be easier to understand and more satisfying for the user.


Thought notes on the work process

Density-based spatial clustering of applications with noise (DBSCAN)
- [DBSCAN - Wikipedia](https://en.wikipedia.org/wiki/DBSCAN)
- [DBSCAN — scikit-learn 1.5.2 documentation](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.DBSCAN.html)

The original data is below, how should this be clustered?
- ![image](https://gyazo.com/4c53444cfe6888501007550891140609/thumb/1000) [[Public Opinion Map 3970 UMAP]]

DBSCAN has a parameter eps that determines how close points are considered as proximity and a parameter min_samples that determines how many points can be discarded as outliers
So I observed what happens under what parameters.

![image](https://gyazo.com/d6e9a06a53a2bf02680914a2f18fddb4/thumb/1000)
- There are 3970 original data, and I felt that determining min_samples as 5 or 10 was too ad hoc, so I set it as a ratio to the original data.
    - In this use case, because of the independence of the original data, the data is randomly thinned by half when there are half as many people, which is reasonable because in that case all cluster members are halved.
- Those determined to be outliers were colored light gray.
    - It's important to visualize the results, you know, "We've got five clusters!" and then you come up with this, I'd be tempted to say, "Start over! I'd say, "Redo it!
        - ![image](https://gyazo.com/74f7654f8031ac018d3849e295b535ac/thumb/1000)
        - This is considered an outlier because the eps are too small and most of them fall apart.
        - You might want to look at "Percentage of data discarded as outliers."
- In terms of not throwing away too much data, I would prefer this one of these 15 ways
    - ![image](https://gyazo.com/8a4dc6a47ddfa51005fbc8fd787bb830/thumb/1000)
    - On the other hand, as for the larger clusters with more content, I'd like to see a little more separation.
    - > Largest cluster label: 0, Size: 3313

central cluster
![image](https://gyazo.com/ca78ba9feeb5beabee68258e4128cdc9/thumb/1000)
![image](https://gyazo.com/2ede642899c3f91ba27476630daa82f7/thumb/1000)
- Ummm, the diagonal line between the two is subjectively preferable, but it's still an outlier.
    - ![image](https://gyazo.com/868a75c921455b846d041acd1ca2a45c/thumb/1000)![image](https://gyazo.com/8f47923a4850a422f8cd1d6b127b5db3/thumb/1000)
    - If you increase eps to reduce outliers, clusters will be merged
    - Hmmm, I wonder if this is more a problem with interpreting DBSCAN "outliers" as "data that is discarded because it is an outlier that is far away" and should we interpret it as "data that is between two clusters and hard to say which side it is on"?
        - ![image](https://gyazo.com/a7b9acd91aa50cf79544b11fff78fde0/thumb/1000)
        - We want to separate A from B, so where do we draw the line?"
            - Isn't this question wrong in the first place? that this question is wrong in the first place, isn't it?
            - Drawing a boundary line is putting in the assumption that it is divisible by a line of no thickness.
            - In reality, many things in the world do not have clear boundaries, but are divided across a wide "neither-here-nor-there" zone
    - I was surprised at first that this part of the chord was split.
        - ![image](https://gyazo.com/1868854c22611da841d329133a1d4e76/thumb/1000)
        - You can see why when you see less eps and higher ratios.
            - (I initially went through with "too many outliers," but this is actually important.)
            - ![image](https://gyazo.com/a2298c62327fa77c07790025c226b0c0/thumb/1000)
            - I, as a human being, had not noticed this just by eyeballing the two-dimensional diagram, but there is a zone of high concentration at the tip of the chasus
                - KDE]([[Kernel density estimation]]) for easy understanding of density is like this
                - ![image](https://gyazo.com/4e9837dedb502ad1e9f52e4f334e0258/thumb/1000)
            - The territory is expanding from this zone of density to the extent of eps, which is considered a landlocked area.

I saw the KDE and thought I'd rather KDE with a wider band.
- ![image](https://gyazo.com/fb307a29abb597198aff6c47bdc4034f/thumb/1000)
    - [Let's start with the broad strokes.
    - First of all, we assume the world's perception that this kind of thing exists.
- Among them, the distribution of opinions, especially in the high-density zone, is thus
- ![image](https://gyazo.com/5eb99e21a33cd7a7e65d68bfb98457aa/thumb/1000)
- And then, AI provides explanations for these "dense clusters".
- I think that's a good way to explain it.

I've summarized at the top of the page regarding this realization.

Other Methods
- With respect to the central cluster, we are trying to cluster based on the "first UMAP for all data", but there is a way to go back to the original data and UMAP it again.
    - But I think it's too difficult to explain for the general public.
- For the original data in this case, each axis is for and against data, so there is an option to use [[For and Against Density Indication]] without clustering.
    - Cannot be used for UMAP embedding of natural language
        - In this case, is the approach to let the cluster itself be discovered by the LLM?

I got feedback on this article.
- next:  [[Careful clustering of tSNE results]]

---
This page is auto-translated from [/nishio/UMAPの結果をクラスタリングするべきか](https://scrapbox.io/nishio/UMAPの結果をクラスタリングするべきか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.