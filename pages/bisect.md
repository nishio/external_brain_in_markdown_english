---
title: "bisect"
---

- [[dichotomous search]]
First place over k" is RIGHT, "first place over k" is LEFT
python

```
>>> import bisect
>>> xs = [1, 2, 4, 4, 5]
>>> [bisect.bisect_left(xs, x) for x in range(7)]
[0, 0, 1, 2, 2, 4, 5]
>>> [bisect.bisect_right(xs, x) for x in range(7)]
[0, 1, 2, 2, 4, 5, 5]
```

![image](https://gyazo.com/357c7b0a1c8a25f8bf415ae5bbc791fa/thumb/1000)

[[atcoder]]

---
This page is auto-translated from [/nishio/bisect](https://scrapbox.io/nishio/bisect) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.