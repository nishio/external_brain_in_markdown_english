---
title: "I wrote down the array access and it slowed down."
---

You should not try to fine-tune a high-level language.

587 ms
python

```
    if rank[x] < rank[y]:
        parent[x] = y
    else:
        parent[y] = x
        if rank[x] == rank[y]:
            rank[x] += 1
```

[https://judge.yosupo.jp/submission/12671](https://judge.yosupo.jp/submission/12671)

609 ms
python

```
rx = rank[x]
ry = rank[y]
if rx < ry:
    parent[x] = y
else:
    parent[y] = x
    if rx == ry:
        rank[x] = rx + 1
```

[https://judge.yosupo.jp/submission/12673](https://judge.yosupo.jp/submission/12673)

---
This page is auto-translated from [/nishio/配列アクセスをメモしたら遅くなった](https://scrapbox.io/nishio/配列アクセスをメモしたら遅くなった) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.