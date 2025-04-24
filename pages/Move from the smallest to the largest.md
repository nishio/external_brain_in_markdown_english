---
title: "Move from the smallest to the largest"
---

Techniques for speeding up merging of multiple sets

- When merging something of size X into something of size Y, it is assumed to hang O(X).
python

```
for x in X:
    Y.add(x)
```

- Repeat the merging of the elements of a set of size N into a set of size 1 with only the elements of each
    - In a naive way, O(N) merges N-1 times, so O(N^2)
    - ![image](https://gyazo.com/5b592048a795de209b82cc446fbfd768/thumb/1000)

- If we decide to merge the smaller one into the larger one, this becomes O(NlogN)
    - Discussion:.
        - Let X be the smaller one.
        - Each time you merge, the size of the set will be 2X or larger.
        - If we look at an element x, it is at most $\log_2 N$ times the smaller of the two.
        - ![image](https://gyazo.com/82116cda69fb4047b785b3d8f7154fb1/thumb/1000)

---
This page is auto-translated from [/nishio/小さい方から大きい方へ移す](https://scrapbox.io/nishio/小さい方から大きい方へ移す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.