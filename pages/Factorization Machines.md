---
title: "Factorization Machines"
---

- `[S. Rendle, 2010]` [PDF](https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf)
- A naive treatment of second-order combinatorial features would result in D^2 parameters with the number of features as D
- Then, we assign a K-dimensional vector to each feature, and apply the constraint that the weights of the combinatorial features are the inner products of the K-dimensional vectors.
- That is, like this $\hat{y}(\mathbf{x}) := w_0 + \sum_{i=1}^n w_i x_i + \sum_{i=1}^n \sum_{j=i+1}^n \langle \mathbf{v_i}, \mathbf{v_j} \rangle x_i x_j$
- This reduces the number of parameters to D*K


---
This page is auto-translated from [/nishio/Factorization Machines](https://scrapbox.io/nishio/Factorization Machines) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.