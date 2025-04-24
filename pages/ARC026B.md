---
title: "ARC026B"
---

[B - complete number](https://atcoder.jp/contests/arc026/tasks/arc026_2)[B - complete number](https://atcoder.jp/contests/arc026/tasks/arc026_2)
- ![image](https://gyazo.com/3ce26f4ee4e9e40a944a3ec5ac30aee4/thumb/1000)
- Thoughts.
    - Huh? Can't [[irreducible enumeration]] be done in square root order, so we can naively find and add it in time?
python

```
def solve(N):
    s = sum(get_divisors(N))
    if s == 2 * N:
        return "Perfect"
    if s < 2 * N:
        return "Deficient"
    return "Abundant"
```

    - AC
---
This page is auto-translated from [/nishio/ARC026B](https://scrapbox.io/nishio/ARC026B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.