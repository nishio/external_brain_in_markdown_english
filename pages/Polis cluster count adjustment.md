---
title: "Polis cluster count adjustment"
---

Written in Polis's Clojure-implemented math server.

math/src/polismath/math/conversation.clj:509
clj

```
(range 2 (inc (max-k-fn group-cluster-proj (:max-k opts')))))]))
```

:142
clj

```
(merge {:n-comps 2 ; does our code even generalize to others?
        :pca-iters 100
        :base-iters 100
        :base-k 100
        :max-k 5
        :group-iters 100
        ;; These three in particular we should be able to tune quickly
        :max-ptpts 100000
        :max-cmts 10000
        :group-k-buffer 4}
  opts))
```


If this `(range 2` and `:max-k 5` are each 4, we would have 4 definite clusters.

---
This page is auto-translated from [/nishio/Polisのクラスタ数調整](https://scrapbox.io/nishio/Polisのクラスタ数調整) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.