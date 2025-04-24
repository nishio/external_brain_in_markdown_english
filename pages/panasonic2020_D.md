---
title: "panasonic2020_D"
---

[D - String Equivalence](https://atcoder.jp/contests/panasonic2020/tasks/panasonic2020_d)
- ![image](https://gyazo.com/a8b4b439b08c41341e3abcb3d0b259b3/thumb/1000)
- Thoughts.
    - Relationships that are the same character are transitive
        - So we can figure out how to split the set of integers less than or equal to N into one or more sets.
    - From the conditions of the standard form, the number of occurrences at a point is less than or equal to the maximum number of occurrences up to that point, x+1.
        - Otherwise, the replacement of that number with x+1 would be smaller and contradict the conditions of the standard form.
    - So it looks good for DFS to choose the options in ascending order up to the number +1 that appeared before at each point
- Official Explanation OK

---
This page is auto-translated from [/nishio/panasonic2020_D](https://scrapbox.io/nishio/panasonic2020_D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.