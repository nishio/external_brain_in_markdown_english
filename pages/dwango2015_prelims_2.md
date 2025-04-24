---
title: "dwango2015_prelims_2"
---

[B - Nikoniko string](https://atcoder.jp/contests/dwango2015-prelims/tasks/dwango2015_prelims_2)
- How many ways are there to cut a repeating string of "25" from a given string [[enumeration]]?
- Given a substring consisting of N consecutive 25's, [[trigonometric number]] tri(N) is the number of pieces that can be cut from the substring.
- It would be faster to use [[(computer) regular expression]] to find out what's going on, rather than looping through it yourself.
- Because I didn't make it test-driven because I thought it would be easy, I forgot the specification that "if parentheses are used in a regular expression, findall will return only that range" and I WA'd.
    - `(? : )` is a non-capturing grouping
python

```
import re 

def tri(x):
    return x * (x + 1) // 2

S = input()
ret = 0
print(sum(tri(len(s) // 2) for s in re.findall("(?:25)+", S)))
```

[submitted #15126969 - dwango programming contest](https://atcoder.jp/contests/dwango2015-prelims/submissions/15126969)

---
This page is auto-translated from [/nishio/dwango2015_prelims_2](https://scrapbox.io/nishio/dwango2015_prelims_2) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.