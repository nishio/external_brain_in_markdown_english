---
title: "PAST4L"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4L
[L - Apartment Renovation](https://atcoder.jp/contests/past202010-open/tasks/past202010_l)
- Thoughts.
    - Answer the number of adjacent value matches each time by adding to one of the following: odd, even, or one point.
    - Since the query is 10^5, per query is a constant or log
    - One point change is okay, but odd numbers are a problem.
        - If you have an even-numbered minus an odd-numbered difference, it is just a Range Add.
        - Range Add to find the number of 0's in the whole?
        - Don't Range Add, just look for the -x ones.
            - Constant order if you can have the frequency table in an array.
            - 10^9, so it's impossible.
            - Can we use hash?
        - What do you do when you renew a point?
            - calculate backwards
    - AC
python

```
def main():
    N, Q = map(int, input().split())
    HS = list(map(int, input().split()))
    from collections import defaultdict
    freq = defaultdict(int)
    for i in range(N - 1):
        d = HS[i] - HS[i + 1]  # odd - even
        if i & 1:
            d = -d
        freq[d] += 1

    odd_height = 0
    for _q in range(Q):
        q = list(map(int, input().split()))
        if q[0] == 1:
            odd_height += q[1]
            print(freq[-odd_height])
        elif q[0] == 2:
            odd_height -= q[1]
            print(freq[-odd_height])
        else:
            i = q[1] - 1
            add = q[2]
            if i > 0:
                d = HS[i] - HS[i - 1]
                if i & 1:
                    d = -d
                freq[d] -= 1
            if i < N - 1:
                d = HS[i] - HS[i + 1]
                if i & 1:
                    d = -d
                freq[d] -= 1

            HS[i] += add
            if i > 0:
                d = HS[i] - HS[i - 1]
                if i & 1:
                    d = -d
                freq[d] += 1
            if i < N - 1:
                d = HS[i] - HS[i + 1]
                if i & 1:
                    d = -d
                freq[d] += 1
            print(freq[-odd_height])
```


Similar to [[PAST1H]].

---
This page is auto-translated from [/nishio/PAST4L](https://scrapbox.io/nishio/PAST4L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.