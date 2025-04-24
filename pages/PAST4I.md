---
title: "PAST4I"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4I
[I - Pizza](https://atcoder.jp/contests/past202010-open/tasks/past202010_i)
- Thoughts.
    - Finally, a huge N problem.
            - Find the point where [[Range Sum of Circumference]] is the largest.
        - Double the cumulative sum
        - Still, if the starting and ending points are free, the order of the square
            - [[inchworm law]].
        - Which should I do at the time of the equal?
            - Shrink?
            - When it's equal, the answer is zero, so you're done.
            - I went through it, so I'm good.
python

```
def solve(N, AS):
    import sys
    INF = sys.maxsize

    from itertools import accumulate
    acc = list(accumulate(AS + AS)) + [0]

    def rangeSum(start, end):
        return acc[end - 1] - acc[start - 1]

    start = 0
    end = 1
    ret = INF
    total = rangeSum(0, N)
    while True:
        x = rangeSum(start, end)
        y = total - x
        d = x - y
        ret = min(abs(d), ret)
        if d < 0:
            if end == 2 * N - 1:
                break
            end += 1
        else:
            start += 1
    return ret
```


---
This page is auto-translated from [/nishio/PAST4I](https://scrapbox.io/nishio/PAST4I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.