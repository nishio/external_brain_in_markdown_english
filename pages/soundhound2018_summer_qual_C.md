---
title: "soundhound2018_summer_qual_C"
---

[C - Ordinary Beauty](https://atcoder.jp/contests/soundhound2018-summer-qual/tasks/soundhound2018_summer_qual_c)
- ![image](https://gyazo.com/6027131e902305a403650ddd77ea4749/thumb/1000)
- Thoughts.
    - The problem of finding the mean of the number of numbers whose difference between two neighbors is d for a sequence of length m in n^m ways.
    - If we can find the time of m-1, we can find the time of m
        - Because the increment is determined independently of the m-1 state.
    - I thought it was an expected value DP, but since it doesn't depend on the immediately preceding situation, it can be simply multiplied.
    - Number of cases where the difference between two values is d
        - n when d=0
        - 2(n-d) when d<=n
    - Columns of length m have pair m-1
        - When d=0 $(m-1)/n$
        - When d<=n $2(m-1)(n-d)/n^2$
    - [[Official Explanation OK]]
---
This page is auto-translated from [/nishio/soundhound2018_summer_qual_C](https://scrapbox.io/nishio/soundhound2018_summer_qual_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.