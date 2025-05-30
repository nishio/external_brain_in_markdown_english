---
title: "Difference between np.dot, np.tensordot, and np.matmul"
---

Now that I know the expressive method [[np.einsum]], I'll check the difference by expressing np.dot, np.tensordot, and np.matmul with np.einsum, respectively.


python

```
import numpy as np

def same_matrix(A, B):
    return (A.shape == B.shape) and all(A.flatten() == B.flatten())


# 3-dim
T1 = np.arange(27).reshape(3, 3, 3)
T2 = np.arange(27).reshape(3, 3, 3) + 1

assert same_matrix(
    np.einsum('ijk,jkl->il', T1, T2),
    np.tensordot(T1, T2))

assert same_matrix(
    np.einsum('ijk,lkm->ijlm', T1, T2),
    np.dot(T1, T2))

assert same_matrix(
    np.einsum('ijk,ikm->ijm', T1, T2),
    np.matmul(T1, T2))
```


In addition, I did it in 4 dimensions and 2 dimensions.
python

```
# 4-dim
T1 = np.arange(81).reshape(3, 3, 3, 3)
T2 = np.arange(81).reshape(3, 3, 3, 3) + 1

assert same_matrix(
    np.einsum('ijkl,klmn->ijmn', T1, T2),
    np.tensordot(T1, T2))

assert same_matrix(
    np.einsum('ijkl,mnlo->ijkmno', T1, T2),
    np.dot(T1, T2))

assert same_matrix(
    np.einsum('ijkl,ijlm->ijkm', T1, T2),
    np.matmul(T1, T2))


# 2-dim
T1 = np.arange(9).reshape(3, 3)
T2 = np.arange(9).reshape(3, 3) + 1

assert same_matrix(
    np.einsum('ij,ij->', T1, T2),
    np.tensordot(T1, T2))

assert same_matrix(
    np.einsum('ij,jk->ik', T1, T2),
    np.dot(T1, T2))

assert same_matrix(
    np.einsum('ij,jk->ik', T1, T2),
    np.matmul(T1, T2))
```



# Commentary

python

```
 assert same_matrix(
     np.einsum('ijk,jkl->il', T1, T2),
     np.tensordot(T1, T2))
```


tensordor crushes the two behind T1 and the two in front of T2. Therefore, jk in ijk and jk in jkl are collapsed and il remains. You can specify the number of collapses by an option.

python

```
 assert same_matrix(
     np.einsum('ijk,lkm->ijlm', T1, T2),
     np.dot(T1, T2))
```


DOT crushes the last one in T1 and the second from the end in T2. So the k in ijk and the k in lkm are crushed, leaving ijlm.

python

```
 assert same_matrix(
     np.einsum('ijk,ikm->ijm', T1, T2),
     np.matmul(T1, T2))
```


matmul assumes multiplication of tensors of the second order. Therefore, the basis of matmul is "multiplying jk and km to make jm (jk,km->jm)", and then "i values are stacked in one square of the matrix" is treated as ijk,ikm->ijm as a result. In addition, `np.matmul(np.ones((2, 1, 3, 4)), np.ones((1, 5, 4, 6)))` is valid because it broadcasts the i's.
#NumPy
---
This page is auto-translated from [/nishio/np.dot, np.tensordot, np.matmulの違い](https://scrapbox.io/nishio/np.dot, np.tensordot, np.matmulの違い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.