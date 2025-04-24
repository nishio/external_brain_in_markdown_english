---
title: "PAST5F"
---

[F - A Touch of Fiction](https://atcoder.jp/contests/past202012-open/tasks/past202012_f)
![image](https://gyazo.com/82689f73ea9cacb95a4584a9b4618956/thumb/1000)

- 2 ** 14 == 16384
- 14 * 13 * 12 == 364
- This is a good size to explore all
    - For all 14 methods of selecting chemicals, check all 364 rules up to a maximum of 364 to check "because it hasn't exploded" and "if it's a flash, what's the dangerous chemical?".
- WA by misunderstanding the problem conditions.
    - Not "the number of chemicals already mixed" at a touch of a button.
    - Nor is it "the number of rules in a state of flux."
    - The answer is the size of the set of "chemicals that have not yet been added to the set of rules for the touchy situation.
python

```
def solve(N, rules):
    ret = 0
    for subset in range(2 ** N):
        danger = []
        for rs in rules:
            hit = 0
            for r in rs:
                if subset & (1 << (r - 1)):
                    hit += 1
                else:
                    d = r
            if hit == 3:
                danger = []
                break
            if hit == 2:
                danger.append(d)

        ret = max(ret, len(set(danger)))

    return ret
```



---
This page is auto-translated from [/nishio/PAST5F](https://scrapbox.io/nishio/PAST5F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.