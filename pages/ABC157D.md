---
title: "ABC157D"
---

[D - Friend Suggestions](https://atcoder.jp/contests/abc157/tasks/abc157_d)
- ![image](https://gyazo.com/d99292d29989491cb448463d83cd6467/thumb/1000)
- Thoughts.
    - I wondered at first what the fourth of the candidate friend conditions was all about, but in essence it just says "it's a consolidation."
    - But asking for the consolidated component first could result in "all consolidated".
    - The vertex is 10^5, so it can't be on the order of squared.
    - You take advantage of the fact that the number of sides is limited to 10^5.
    - First, find the connected components using [[UnionFind]] and initialize them with size -1, and then for each friendship and block relation, if both ends of the connected components are the same, set both ends to -1.
    - [[Official Explanation OK]]

[[ABC157]]

---
This page is auto-translated from [/nishio/ABC157D](https://scrapbox.io/nishio/ABC157D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.