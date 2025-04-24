---
title: "abc151_e"
---

[https://atcoder.jp/contests/abc151/tasks/abc151_e](https://atcoder.jp/contests/abc151/tasks/abc151_e)
- Thoughts.
    - There may be an algorithmically contrived route, but a mathematical transformation seems like a good idea.
    - max(S), the max of a subset, is max(A) if it contains one or more max(A)
    - Conversely, what is not is the number of combinations [[have an after-event]] that choose K from N-c(max(A)) numbers where c(x) is the number of numbers greater than or equal to x.
    - So if we sort and count, we know c, and we can also find the number of times it maxes out for each number.
            - [[binomial coefficient table]] is fast if it is created.
        - [[The sum of the differences is the difference between the sums]], and only the max term can be used to find the story first
        - $\sum_{s\in S} (f(s) - g(s)) = \sum_{s\in S} f(s) - \sum_{s\in S} g(s)$
    - The same argument can be made about min, and if you pull it, you get the answer.
- Official Explanation
    - Duplicate values are handled a little differently.
    - Given the same values A1 and A2, the maximum value of A1 is the sum of "selecting A1 and choosing K-1 from A2 and onward" and "selecting A2 and choosing K-1 from A3 and onward," which is indeed an inversion.

---
This page is auto-translated from [/nishio/abc151_e](https://scrapbox.io/nishio/abc151_e) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.