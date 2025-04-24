---
title: "ABC125C"
---

[C - GCD on Blackboard](https://atcoder.jp/contests/abc125/tasks/abc125_c)
- ![image](https://gyazo.com/be7a37e747fc2d81355ee27815fa105a/thumb/1000)
- Thoughts.
    - If the remaining gcd after removing one is 1, then it's 1 no matter what.
        - Because the gcd can never be greater than the argument.
    - In other words, "Find the maximum value of gcd with one removed."
    - This is [[obsolete rule prohibiting match-ups between wrestlers from the same group of stables]].
            - [[Cumulative product from left to right]] is OK
- Official Explanation
    - Same policy
    - He's using 0 as a sentry.
    - $\gcd(0, X) = \gcd(X, 0) = X$
    - Python standard gcd also behaves this way

---
This page is auto-translated from [/nishio/ABC125C](https://scrapbox.io/nishio/ABC125C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.