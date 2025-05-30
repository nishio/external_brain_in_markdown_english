---
title: "Implement PCA without PCA"
---

python

```
import numpy as np
# Prepare appropriate data 5 dimensions 6 cases of data
data = np.random.random((6, 5))
# Subtract average
d2 = data - data.mean(axis=0)
# Create a covariance matrix
cov = np.einsum("ij,ik->jk", d2, d2)

# The covariance matrix is a square matrix of the dimensions of the data
>>> cov.shape
(5, 5)

# Decompose the covariance matrix into eigenvalues
>>> np.linalg.eig(cov)
(array([1.34012189, 0.77663231, 0.58201555, 0.08694709, 0.03991043]),
 array([[ 0.67869952,  0.35340645, -0.37436676,  0.50602025,  0.13514392],
        [ 0.45792096,  0.20519401,  0.77490418, -0.08403411, -0.37505412],
        [-0.46695028,  0.17178326,  0.04681577,  0.68316922, -0.53248104],
        [-0.26671759,  0.89310368, -0.08178549, -0.34559589,  0.07142937],
        [-0.20123254,  0.07652205,  0.50049221,  0.38823327,  0.74325791]]))

# PCA implementation for comparison
from sklearn.decomposition import PCA
# Fit to data
m = PCA().fit(data)

# Show principal component axes
>>> m.components_
array([[ 0.67869952,  0.45792096, -0.46695028, -0.26671759, -0.20123254],
        [ 0.35340645,  0.20519401,  0.17178326,  0.89310368,  0.07652205],
        [-0.37436676,  0.77490418,  0.04681577, -0.08178549,  0.50049221],
        [ 0.50602025, -0.08403411,  0.68316922, -0.34559589,  0.38823327],
        [ 0.13514392, -0.37505412, -0.53248104,  0.07142937,  0.74325791]])

# Comparing the results of the eigenvalue decomposition of the covariance matrix with the principal component axes of the PCA, the difference is almost zero
>>> np.linalg.eig(cov)[1] - m.components_.T
array([[-4.44089210e-16,  1.11022302e-16,  4.99600361e-16,
         1.11022302e-16,  1.66533454e-16],
       [-2.22044605e-16, -6.66133815e-16,  4.44089210e-16,
        -3.88578059e-16, -1.11022302e-16],
       [ 1.11022302e-16, -3.05311332e-16, -2.56739074e-16,
        -3.33066907e-16,  3.33066907e-16],
       [-2.22044605e-16,  0.00000000e+00,  2.08166817e-15,
         3.33066907e-16, -3.60822483e-16],
       [ 2.22044605e-16, -1.02695630e-15, -1.11022302e-16,
         6.66133815e-16,  0.00000000e+00]])

# Relationship to Singular Value Classification (SVD) (same except that some of the signs on the axes are reversed)
>>> -np.linalg.svd(d2)[2]
array([[ 0.67869952,  0.45792096, -0.46695028, -0.26671759, -0.20123254],
       [ 0.35340645,  0.20519401,  0.17178326,  0.89310368,  0.07652205],
       [-0.37436676,  0.77490418,  0.04681577, -0.08178549,  0.50049221],
       [-0.50602025,  0.08403411, -0.68316922,  0.34559589, -0.38823327],
       [-0.13514392,  0.37505412,  0.53248104, -0.07142937, -0.74325791]])

>>> m.components_
array([[ 0.67869952,  0.45792096, -0.46695028, -0.26671759, -0.20123254],
       [ 0.35340645,  0.20519401,  0.17178326,  0.89310368,  0.07652205],
       [-0.37436676,  0.77490418,  0.04681577, -0.08178549,  0.50049221],
       [ 0.50602025, -0.08403411,  0.68316922, -0.34559589,  0.38823327],
       [ 0.13514392, -0.37505412, -0.53248104,  0.07142937,  0.74325791]])
```


#Principal Component Analysis #Singular Value Decomposition #Covariance Matrix #PCA

    - Create [covariance matrix
    - The covariance matrix is a square matrix of the dimensions of the data
- Do [[eigenvalue decomposition]] of the covariance matrix
    - Display [[principal component axis]] in [PCA
- Comparing the results of the eigenvalue decomposition of the covariance matrix with the principal component axis of the PCA, the difference is almost zero
    - Relationship to [[singular value classification]] ([[SVD]]) (identical except that some of the signs on the axes are reversed)
---
This page is auto-translated from [/nishio/PCAを使わないでPCAを実装](https://scrapbox.io/nishio/PCAを使わないでPCAを実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.