---
title: "ABC103D"
---

[D - Islands War](https://atcoder.jp/contests/abc103/tasks/abc103_d)
- ![image](https://gyazo.com/ced583d7c3c39017177ebf73093c4243/thumb/1000)
- Thoughts.
    - I want to cut a given pass as few times as possible.
    - When you choose one cut, you remove all the paths that can be cut with it, and when you think about the rest, the cut you just made has no effect.
    - So, we should just choose "cut as many paths as possible, including the path at the very end" to Greedy.
    - Is that good enough, and how do you prove it's good?
- Official Explanation
    - My method is "sort by a and cut b-1 of the smallest one."
    - The official explanation is "sort by b and cut b-1 of the smallest one."
    - What difference does it make?
    - Sort by b and when the smallest one is also the smallest in a, there is no difference.
    - when this is not the case
        - ![image](https://gyazo.com/4d873eb41e26ef7bbe5e0664a2c03efa/thumb/1000)
        - Well, surely the official version is more correct.
            - Much like the greedy algorithm in [Interval Scheduling


---
This page is auto-translated from [/nishio/ABC103D](https://scrapbox.io/nishio/ABC103D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.