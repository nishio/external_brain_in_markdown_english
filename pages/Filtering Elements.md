---
title: "Filtering Elements"
---

- The process of removing elements of indefinite length that are included in a specific blacklist
python

```
for x in xs:
	if x in BLACKLIST:
		continue
```

- This is equivalent to having a function f(x) with "element x → 0/1" and calculating xf(x)
![image](https://gyazo.com/fee24159731bab21bb05c9090985a1b4/thumb/1000)
- Can be extended to functions that return real numbers between 0 and 1
        - Inverse pattern of [{0, 1} for real numbers between 0 and 1
    - Describing only the blacklist in the code is equivalent to accumulating only negative examples.
    - If we also accumulate positive examples, the `x in BLACKLIST` part will be replaced by a 2-class classification

- [[neuralization]]

---
This page is auto-translated from [/nishio/要素のフィルタリング](https://scrapbox.io/nishio/要素のフィルタリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.