---
title: "nikkei2019_qual_C"
---

[C - Different Strokes](https://atcoder.jp/contests/nikkei2019-qual/tasks/nikkei2019_qual_c)
- ![image](https://gyazo.com/4ed59c16891725e4088f629ba8803ad0/thumb/1000)
- Thoughts.
    - Think only about the difference D=A-B since all you care about is the final score difference
    - If the back hand does not interfere, the first player wants to take ceil(N/2) pieces from the larger side of D.
    - The back hand naturally gets in the way. The biggest hindrance to the first hand is the biggest D
    - Therefore, the correct answer is the one taken alternately from the one with the largest D.
- Official Explanation
    - careless mistake
        - > D=A-B
    - The difference between those scores would be A+B.

---
This page is auto-translated from [/nishio/nikkei2019_qual_C](https://scrapbox.io/nishio/nikkei2019_qual_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.