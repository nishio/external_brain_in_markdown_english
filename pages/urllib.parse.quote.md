---
title: "urllib.parse.quote"
---

[[Python3]]
By default, the / is not escaped. This can be controlled with the safe parameter.
python

```
>>> urllib.parse.quote("A/B")
'A/B'
>>> urllib.parse.quote("A/B", safe="")
'A%2FB'
```


---
This page is auto-translated from [/nishio/urllib.parse.quote](https://scrapbox.io/nishio/urllib.parse.quote) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.