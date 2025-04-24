---
title: "Dictionary-like usage of Pandas"
---

You want to read a CSV with columns Name and Value in Pandas, and you want to know the Value when Name is a specific value. Assuming that Name is unique.
python

```
import pandas as pd
data = pd.read_csv("t.csv")
v = data[data.Name=="1299c1b7a9e0c2bf41af69c449464a49"]
```


It works as one would expect, as follows
output

```
                                  Name  Value
9979  1299c1b7a9e0c2bf41af69c449464a49   9979 
```


It takes about 64 msec to select one CSV from 1 million rows.
output

```
%timeit data[data.Name=="1299c1b7a9e0c2bf41af69c449464a49"]
10 loops, best of 3: 64.1 ms per loop
```


If you specify index_col in such a case, you can access the following
python

```
data = pd.read_csv("t.csv", index_col="Name")
v = data.Value["1299c1b7a9e0c2bf41af69c449464a49"]
```


It is more than 1,000 times faster.
output

```
%timeit data.Value[key]
1 loop, best of 3: 17.9 µs per loop 
```


Note that even if index_col is not specified when opening, it can be `data.set_index('Name')` later.
---
This page is auto-translated from [/nishio/Pandasの辞書的使い方](https://scrapbox.io/nishio/Pandasの辞書的使い方) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.