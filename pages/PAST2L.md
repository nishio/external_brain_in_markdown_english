---
title: "PAST2L"
---

from  [[Second Algorithm Practical Skills Test]]
PAST2L

![image](https://gyazo.com/c664b1d0acb09d62cb4f03914e6ca3ca/thumb/1000)
[L - Dictionary order minimum](https://atcoder.jp/contests/past202004-open/tasks/past202004_l)
- Thoughts.
    - One range of possible choices for the first letter is defined.
    - The first letter is the smallest of them all.
    - What if there is more than one minimum?
        - Just pick the fastest one.
        - If the smallest in lexicographic order exists with the first other than the first one, it is the smallest in lexicographic order even if the first one is replaced with the earliest one.
    - Determining the first character determines the range of characters that can be selected as the second character.
        - We can repeat this.
- Official Explanation
    - With the above regarding specific implementation, there is a possibility of TLE.
- A new thought.
    - I'll try to be TLE for once.
    - Then figure out how to speed it up.
    - It would be nice to be able to efficiently calculate argmin for a range
        - [[Disjoint Sparse Table]]?
- sample AC
python

```
def solve(N, K, D, AS):
    end = N - D * (K - 1)
    start = 0
    ret = []
    for _i in range(K):
        subseq = AS[start:end]
        if not subseq:
            return [-1]
        v = min(subseq)
        ret.append(v)
        start = AS.index(v, start) + D
        end += D
    return ret
```

    - 8 TLE
- I wonder if [[Disjoint Sparse Table]] is the way to go to speed up the process.
- Since the range only shifts backward, [[priority queue]] is fine.
    - Style to skip reading invalid values
        - [[Slide Range Argmin with priority queue]]
- AC
python

```
def solve(N, K, D, AS):
    from heapq import heappush, heappop, heapify
    end = N - D * (K - 1)
    start = 0
    ret = []
    queue = [(AS[i], i) for i in range(start, end)]
    heapify(queue)
    for _i in range(K):
        if start >= end:
            return [-1]
        while True:
            v, i = heappop(queue)
            if start <= i < end:
                break
        ret.append(v)
        start = i + D
        for i in range(end, min(end + D, N)):
            heappush(queue, (AS[i], i))
        end += D
    return ret
```



---
This page is auto-translated from [/nishio/PAST2L](https://scrapbox.io/nishio/PAST2L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.