---
title: "PAST4K"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4K
[K - number of falls](https://atcoder.jp/contests/past202010-open/tasks/past202010_k)
- Thoughts.
        - [[number of events (e.g. accidents, crimes, meetings, housing starts, hits on a web page)]]
        - Consider what happens when combined
            - The number of overturns in the combined columns is obtained from their respective overturns and frequency tables [[ACLPC L]].
        - The maximum n when calculated alone before combining is 10^5.
        - what to do about it
            - [https://ikatakos.com/pot/programming_algorithm/dynamic_programming/inversion](https://ikatakos.com/pot/programming_algorithm/dynamic_programming/inversion)
                - [[Fennic tree]] Apparently.
        - Samples came through, but WA.
            - I also do TLEs.
        - Test if WA disappears by shifting 1
            - no good
        - The much was 10^9!
    - WA gone but 3 TLE
        - Inline deployment, if this doesn't work, don't.
        - It didn't work.
    - What more can you do?
        - Why is there 5 seconds to time out when it's 3 x 10^5 to begin with?
    - So 300,000 is no good, but 100,000 each is OK?
        - Still, 3 TLE.
    - I tried Cython, but no luck.
    - Should it be written in C++?
- Official Explanation
    - Good policy.
    - It's not a good idea to use a phoenix tree to find the number of overturns every time the same column is used repeatedly.
        - The number of falls and frequency table should have been preprocessed.
    - The reason why the sum of column lengths is kept small is that it is not TLE to use a phoenix tree in preprocessing, but the intention is not to use it for every query because the query may choose only long columns.
- AC
python

```
def solve(K, seqs, Q, BS):
    MOD = 10 ** 9
    N = 20

    invs = []
    freqs = []
    for i in range(K):
        init(N)
        freq = [0] * 21
        inv = 0
        for a in seqs[i]:
            bit_add(a, 1)
            inv += bit_sum(N) - bit_sum(a)
            freq[a] += 1
        invs.append(inv)
        freqs.append(freq)

    ret = 0
    freq = [0] * 21
    for b in BS:
        ret += invs[b - 1]
        f = freqs[b - 1]
        for i in range(1, 21):
            for j in range(i + 1, 21):
                ret += f[i] * freq[j]

        for i in range(1, 21):
            freq[i] += f[i]
        ret %= MOD

    return ret
```



---
This page is auto-translated from [/nishio/PAST4K](https://scrapbox.io/nishio/PAST4K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.