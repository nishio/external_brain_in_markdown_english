---
title: "Aggregate difficult to divide"
---

![image](https://gyazo.com/074de177bd8d8dc1505ae0505e41e18b/thumb/1000)
- When you want to divide the elements of a set by type and then perform an aggregate f on them, but the cost of the division is high
- If f is a function that can be realized by repeated binary operations
    - Examples: sum, min
- Aggregation can be done without dividing the data in advance

python

```
for x in S:
    subgroup[typeof(x)].append(x)
for t, xs in subgroup:
    result[t] = f(xs)
```


python

```
for x in S:
    result[typeof(x)].update(x)
```


- Related to [[attention mechanism]]?

---
This page is auto-translated from [/nishio/分割困難な集計](https://scrapbox.io/nishio/分割困難な集計) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.