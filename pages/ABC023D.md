---
title: "ABC023D"
---

from  [[Typical ideas for coming up with solutions in competitive programming]]

[D - Shooting King](https://atcoder.jp/contests/abc023/tasks/abc023_d)
- ![image](https://gyazo.com/68e0e3d12b92e4c1feaeb010f603dd63/thumb/1000)
- I want to minimize the maximum penalty
    - [[Minimize Maximum]]
- Penalties increase over time, which is tricky.
    - And it's not the sum of the penalties, but the maximum.
        - With harmony, the story is easy to tell because the order can be swapped.
    - Is the order determined by some greedy method?
    - It's not just a matter of taking from the biggest one.
        - With an initial value of 100 and an increase of 1, and an initial value of 90 and an increase of 100, the latter should come first.
        - Rather, "the next highest value shall be the current one" is correct?
- Official Explanation
    - Prepare a provisional "divide by this height" limit, and divide in order of decreasing time remaining.
        - [[Maximization with bisection search.]] Pattern
    - If you cannot think of a way to solve the maximization of f(x) directly by a greedy method, you can make it a problem to determine the existence of a solution for f(x) < X. This makes it easier to find a greedy algorithm, because "If there is a solution, find one, even if it is not the largest.
    - This time it is the minimization of the maximum, so [[The inequality of the max is the inequality AND]] turns it into a small subproblem
        - If max(f(x))<t, then f(x)<t

---
This page is auto-translated from [/nishio/ABC023D](https://scrapbox.io/nishio/ABC023D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.