---
title: "ABC146D"
---

[D - Coloring Edges on Tree](https://atcoder.jp/contests/abc146/tasks/abc146_d)
- ![image](https://gyazo.com/f92ad9c821a31ec19ce1d7da94a425ee/thumb/1000)
- Thoughts.
    - It seems obvious without having to contemplate it, but I guess I'll have to verbalize it.
    - There is no confluence because it is a tree, which means that vertices that came from the parent with an edge of color X can be painted in any color except X, thereby creating no inconsistency.
    - Minimum number of colors required is the maximum number of vertices
    - Just paint the appropriate vertex as a root.
- Official Explanation
    - I agree

---
This page is auto-translated from [/nishio/ABC146D](https://scrapbox.io/nishio/ABC146D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.