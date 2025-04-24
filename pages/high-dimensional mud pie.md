---
title: "high-dimensional mud pie"
---

from  [[Careful clustering of tSNE results]]
high-dimensional mud pie

How high-dimensional is the central cluster?
python

```
# PCA runs and cumulative contribution curves
pca = PCA()
pca.fit(matrix2)

# Calculation of Contribution Ratio and Cumulative Contribution Ratio
explained_variance_ratio = pca.explained_variance_ratio_
cumulative_explained_variance = np.cumsum(explained_variance_ratio)

# Plot the cumulative contribution curve
plt.figure(figsize=(8, 6))
plt.plot(range(1, len(cumulative_explained_variance) + 1), cumulative_explained_variance, marker='o')
plt.xlabel("Number of Components")
plt.ylabel("Cumulative Explained Variance")
plt.title("Cumulative Explained Variance by Number of PCA Components")
plt.grid(True)
plt.show()
```

![image](https://gyazo.com/48afd7a540737ef468ec2177d166a5fc/thumb/1000)

![image](https://gyazo.com/94fdf5b4528bf42a73a96810abf76cdf/thumb/1000)

![image](https://gyazo.com/8638a83416c1ad44632d1c36efd20256/thumb/1000)


![image](https://gyazo.com/f65d4c300d1bee9d4f9413af574f0af1/thumb/1000)
- What kind of phenomenon is this?


---
This page is auto-translated from [/nishio/高次元泥団子](https://scrapbox.io/nishio/高次元泥団子) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.