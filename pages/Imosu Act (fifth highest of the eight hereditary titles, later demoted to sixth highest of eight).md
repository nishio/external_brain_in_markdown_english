---
title: "Imosu Act (fifth highest of the eight hereditary titles, later demoted to sixth highest of eight)"
---

- Add the same value to a range of arrays
    - $A_i ← A_i + X[s \le i < e]$ where s: start, e: end
    - This query is done Q times
    - O(NQ) when implemented naively.
    - Add only the beginning and end of the range first.
    - $B_i ← B_i + X[i = s] - X[i=e]$
    - Then take the [[cumulative sum]] and you get the same thing: O(N+Q)
    - $A_i ← A_{i-1} + B_i$
    - It's like calculating in derivative form and then integrating at the end.

- [imos law - imos laboratory (imos laboratory)](https://imoz.jp/algorithms/imos_method.html)
    - >  [[cumulative sum]] algorithm extended to multi-dimensional and multi-order
- [Cumulative sum and imos (imos) method - Qiita](https://qiita.com/DaikiSuyama/items/67547e14b47cd6360252)

[https://maspypy.com/atcoder-参加感想-2019-02-16abc-155](https://maspypy.com/atcoder-参加感想-2019-02-16abc-155)

[[atcoder]]
[[Range Add]]

---
This page is auto-translated from [/nishio/いもす法](https://scrapbox.io/nishio/いもす法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.