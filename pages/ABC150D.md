---
title: "ABC150D"
---

[D - Semi Common Multiple](https://atcoder.jp/contests/abc150/tasks/abc150_d)
![image](https://gyazo.com/63b89907f3a2e8122ae6c1bfa8ca3e69/thumb/1000)
- Thoughts.
    - [$ 2 b_i = a_i
    - $X = b_k \times (2p + 1)$
    - As for ordinary common multiples, multiplying all of them is a common multiple, but as for antiprime multiples, you're going to have trouble with even numbers included.
    - Think about specific b values
    - 3 5 → 15
    - 3 9 → 9
    - If all the numbers are odd, normal common multiples
    - 2 3
        - Odd multiples of 3 and odd multiples of 2
        - I don't think so.
    - Conclusion.
        - 0 if b contains an even number
        - If not included, find the ordinary least common multiple x, and then the odd multiples of x.
            - Divide M by x to obtain
    - I looked at the sample and it looks good.
- Official Explanation
    - This is an error.
        - 0 if >b contains an even number
    - 2 6 -> There is a 6 which is an odd multiple of 2 and an odd multiple of 6

---
This page is auto-translated from [/nishio/ABC150D](https://scrapbox.io/nishio/ABC150D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.