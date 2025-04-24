---
title: "ABC105C"
---

[C - Base -2 Number](https://atcoder.jp/contests/abc105/tasks/abc105_c)
- ![image](https://gyazo.com/138fd19d56e29837bebffb7acca1e9cf/thumb/1000)
- Thoughts.
        - [[Think in order from smallest to largest]]
    - 1 when 1
    - 110 at 2
        - Since it is 4-2
    - 111 at 3
        - Since 2+1
    - 100 at 4
    - 101 at 5
    - When I was 6...
        - 11010
        - 4+2 is 8-2 and 8 is 16-8.
    - Separate odd and even digits
            - [[Totaled separately for even and odd]]
        - $N = S_0 \times (-2)^0 + S_1 \times (-2)^1 + ... + S_k \times (-2)^k$
        - $= \sum_{i \in (0,2,4,...)} S_i 2^i - \sum_{i \in (1, 3,...)} S_i 2^i$
        - $= S_0 + \sum_{i \in (2,4,...)} S_i 2^i - \sum_{i \in (1, 3,...)} S_i 2^i$

        - mod 4, where the first term is S0, the second term is 0, and the third term is 2S2
        - Therefore, the remainder divided by 4 determines the last two digits.
        - Divide the remainder by four, and the same thing can be repeated.
        - Repeat until it reaches 0.
        - logarithmic order
- Official Explanation
    - Decide from the bottom in the same way.

---
This page is auto-translated from [/nishio/ABC105C](https://scrapbox.io/nishio/ABC105C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.