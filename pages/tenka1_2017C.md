---
title: "tenka1_2017C"
---

[C - 4/N](https://atcoder.jp/contests/tenka1-2017/tasks/tenka1_2017_c)
- ![image](https://gyazo.com/5e556522f06d9b5a2713f8639e0db56c/thumb/1000)
- Thoughts.
    - Let's go through it.
    - 4hnw=N(nh+hw+wn)
        - hmm
    - It's simply made so that if you do a full search, you won't get there in time.
    - Maybe we should do a full search and sample for small values.
    - At any rate, mod n shows that Nhw is a multiple of n and so on.
- Official Explanation
    - Searching for three values will not be done in time, but searching for two values will be done in time.
        - [[All search with wide judgment]]
        - Is f(a,b,c) equal to d for integers a,b,c?" is a narrow decision
        - Find c from a, b, d and ask, "Is c an integer?" is a broad decision


---
This page is auto-translated from [/nishio/tenka1_2017C](https://scrapbox.io/nishio/tenka1_2017C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.