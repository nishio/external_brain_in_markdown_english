---
title: "ABC184E"
---

![image](https://gyazo.com/3b62a4951b2100ef564ece4d0770989b/thumb/1000)
- [E - Third Avenue](https://atcoder.jp/contests/abc184/tasks/abc184_e)

from [[ABC184]]

- Width-first search with increasing distance by 1
- The muddy part is loading the necessary values in a usable form.
    - I wanted the start and finish line to be given separately, not written on a map.
        - [[Put the map in a 1D array]] I had to rewrite the library in a gory way.
    - Nothing particularly interesting there.
- I TLE'd on the width-first search, so I assumed the warp part wasn't a good idea and jitters and TLE'd four times.
    - I had figured out that the same letter warp is only used once, and I was trying to figure out how to avoid trying it twice.
    - Turns out, the cause wasn't there, but where they had a list of "next vertices to visit".
        - AC if you change it to a set.
            - [[AtCoder Failure List]].
python

```
def solve(data):
    to_visit = [START]
    DIR4 = dir4()
    ret = 0
    
    while to_visit:
        new_visit = []
        for p in to_visit:
            if p == GOAL:
                return ret

            v = data[p]
            data[p] = -1
            if v > 0:  # WARP
                for p2 in WARP[v]:
                    data[p2] = 0
                    new_visit.append(p2)
                WARP[v] = []
            for d in DIR4:
                p2 = p + d
                if data[p2] >= 0:
                    new_visit.append(p2)
        to_visit = set(new_visit)
        ret += 1
    return -1
```


---
This page is auto-translated from [/nishio/ABC184E](https://scrapbox.io/nishio/ABC184E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.