---
title: "Finding the next element in a set"
---

Given a value a, I want to find the smallest x such that a < x from the set

The set is represented by a phenic tree with a value range of 0/1.
- `sum(a)`: $\sum_{0 \le i < a} X_i$
- `bisect(s)`: minimum x s.t. sum(x) >= s
at this time
python

```
def find_next(self, pos):
    s = self.sum(pos + 1) + 1
    return self.bisect(s) - 1
```


![image](https://gyazo.com/e13c8b62c13d919d43a658d509c47893/thumb/1000)


---
This page is auto-translated from [/nishio/集合から次の要素を探す](https://scrapbox.io/nishio/集合から次の要素を探す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.