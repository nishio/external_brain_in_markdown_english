---
title: "inverse mapping table"
---

Given $f(x) = y$ make [$ g(y) = x
python

```
for x in all_x:
    g[f[x]] = x
```


Linear-order preprocessing, y to x mapping is of constant order

important point
- Arrays can cause memory errors when the y value range is large.
    - Hash table is one option
    - There is also the option of sorting and dichotomous search
        - The preprocessing would be NlogN and the acquisition would be logN.
- Cannot be restored if there is an x that takes the same y value
        - Must be [[INJECTION]].
    - When not [[onto mapping]], a value to express "there is no corresponding x" and a check to see if it is that value

---
This page is auto-translated from [/nishio/逆写像テーブル](https://scrapbox.io/nishio/逆写像テーブル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.