---
title: "Deep Cluster Extraction"
---

2024-11-30
![image](https://gyazo.com/3df9185b34c8a329ea5ad5c1b48664c9/thumb/1000)

Scripts that find and explain dense chunks of data rather than sorting the entire data into clusters
- [https://github.com/nishio/ai_kj/blob/main/dense_cluster_extruction.ipynb](https://github.com/nishio/ai_kj/blob/main/dense_cluster_extruction.ipynb)
    - [[dense-cluster-extruction]]

background
- [[Talk to the City]] "divides" the "whole" of a given set of data into a specified number of groups.
- Useful in getting a rough idea of what data is available, but often there is a need for "more [[delving into]]"
- This script meets that need by using the intermediate data after Talk to the City's extraction and embedding steps to discover and enumerate "[[dense clusters of opinions]]"

Explanation of usage and implementation
- It is in interactive Jupyter format (IPython Notebook, `*.ipynb`) to demonstrate what results can be obtained, but you can also cut out the Python code parts and use them as Python scripts
    - Visual Studio Code should be easy to run.
        - [Working with Jupyter Notebooks in Visual Studio Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)
- Use HDBSCAN, which Talk to the City uses internally.
- The number of dense clusters extracted is shown as `Num dense clusters 48` after `In [4]` runs
    - There is room for trial and error for parameters since they depend on the number and distribution of the original data.
        - [HDBSCAN — scikit-learn 1.5.2 documentation](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.HDBSCAN.html)
        - `hdb = HDBSCAN(min_cluster_size=5, max_cluster_size=30, min_samples=2)`
        - The larger `min_samples=2` is, the more smoothing effects occur in the density calculation, so the output is more likely to be like "roughly speaking, it's all one lump".
        - `min_cluster_size=5` means "extracting the places where more than 5 cases are densely clustered".
        - The `max_cluster_size=30` was added with the intention of splitting up large clusters of 30 or more entries and looking at them in detail, but it may be better not to use it since it splits up large clusters and creates several clusters with similar contents.
        - It may be better to specify `cluster_selection_method="leaf"`, which is not specified here.
- After saving the results in `In [6]`, an AI commentary is generated from `In [7]`.
    - Prompt has room for ingenuity.
        - `Output the interestingness of the nameplate on a scale of 100 points. Give 0 points to those that are commonplace and 100 points to those that you noticed new things about. I`m thinking that the `part` was not so valid after seeing the results this time.
        - Instead, I feel that it would be more interesting to prompt the participants to list the clusters that introduce a unique perspective and their original points of view.

orthographical variants
- [[Extraction of dense masses]]

---
This page is auto-translated from [/nishio/濃いクラスタ抽出](https://scrapbox.io/nishio/濃いクラスタ抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.