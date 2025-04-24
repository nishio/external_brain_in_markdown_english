---
title: "biclustering"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Biclustering (biclustering) is a technique that performs clustering on both rows and columns simultaneously. While traditional clustering creates similar groups for data rows (e.g., samples), biclustering considers rows and columns (e.g., samples and features) simultaneously and extracts groups (biclusters) such that a certain subset of rows and columns shows a common pattern. biclusters) are extracted.

For example, in gene expression data, genes (rows) and conditions (columns) can be separated simultaneously to find subsets of a particular gene set that show similar patterns under certain conditions. This technique is suitable for discovering potential local patterns in a data matrix and has applications in many areas, including gene expression analysis, bioinformatics, and text mining (document x word matrix analysis).

Biclustering problems are generally computationally expensive and often NP-hard. Therefore, various heuristic, probabilistic, and information-theoretic approaches have been proposed. There are various types of biclusters, including those with constant values, those showing a constant trend in the row or column direction, and those with additive or multiplicative pattern consistency.

In general, biclustering is a powerful tool for extracting meaningful substructures from both rows and columns and for deepening our understanding of data.

Typical implementation examples/tools:
- Python (scikit-learn)
- The [[SpectralCoclustering]] and [[SpectralBiclustering]] classes are provided for easy coding and convenient testing of basic co-clustering (biclustering) methods.
py

```
from sklearn.cluster import SpectralCoclustering
model = SpectralCoclustering(n_clusters=5, random_state=0)
model.fit(data_matrix)
# model.rows_, model.columns_ to get cluster information by row and column
```



---
This page is auto-translated from [/nishio/バイクラスタリング](https://scrapbox.io/nishio/バイクラスタリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.