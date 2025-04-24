---
title: "UMAP of the data for and against"
---

Be careful when [[UMAP]], [[DBSCAN]], [[HDBSCAN]] with data such as a vector of +1 for, -1 against, 0 missing
This is because this type of data often has "overlapping data at the same point," and from the perspective of an algorithm that takes k data points in the neighborhood and calculates density, it appears that there are "very dense clusters.

![image](https://gyazo.com/33db5afa7fee3f182b00dbd64a54e268/thumb/1000)
Diagram of a cluster of clusters that seem to make a lot of sense.
The original data is 5000 vectors of 100 dimensions, where "3% are +1, 3% are -1, and the rest are 0

This is what happens when you turn "the point with only one non-zero value" out of this UMAP plot to red
![image](https://gyazo.com/95c96b22678ea65e678f20b8195cf7d4/thumb/1000)
You can see the red dots like cores in what looked like "meaningful clusters."

If we restrict the UMAP to 4920 "data with two or more non-zero values," we get this
![image](https://gyazo.com/9689803635bc2483f202bf33805ed273/thumb/1000)
What appeared to be a meaningful cluster earlier has mostly disappeared, indicating that it was just an artifact.

Counting the number of pieces
![image](https://gyazo.com/44e6cf0408866a29384d135d7bcacb1b/thumb/1000)
There are 8 origin data and some data that happen to overlap by 2 (there were 12).

This is a plot of only these two overlapping points in red
![image](https://gyazo.com/a975353317cd7b1eec001355ed9d0484/thumb/1000)
The core of the cluster of artifacts can be seen

---

This is not a tricky phenomenon that only happens with generated data, but also with real data
Trial and error clustering with DBSCAN for the following UMAPs obtained from real-world data
![image](https://gyazo.com/ca78ba9feeb5beabee68258e4128cdc9/thumb/1000)

DBSCAN from 2D data did not work very well, so I was trying in 84D space before dimensionality reduction, but it was disturbing that some parameters produced "clusters that excluded what clearly looked like clusters near the center".
![image](https://gyazo.com/2f5bb5b150d2c2ceaa7eb3de6daa4e0c/thumb/1000)

In the process of trying to figure out what caused this, I found that "what looked like a cluster near the center" was a collection of data with few missing values, and the surrounding complex and meaningful shapes were data with many missing values.
![image](https://gyazo.com/66f90b8311c1343c4720c730623b1ca1/thumb/1000)
I noticed the above phenomenon from this result, where the density of data with more missing values is higher.
Originally, this data was `matrix.dropna(thresh=3)`, but when I changed it to `matrix.dropna(thresh=10)`, the UMAP result is as follows
![image](https://gyazo.com/6c91b8174f233a4441bc3c3fc66a7d08/thumb/1000)
Almost all of the complex shapes were artifacts.

- [[UMAP of public opinion map]]

---
This page is auto-translated from [/nishio/賛成反対データのUMAP](https://scrapbox.io/nishio/賛成反対データのUMAP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.