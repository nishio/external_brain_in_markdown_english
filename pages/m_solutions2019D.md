---
title: "m_solutions2019D"
---

[D - Maximum Sum of Minimum](https://atcoder.jp/contests/m-solutions2019/tasks/m_solutions2019_d)
- ![image](https://gyazo.com/f834dc866fa9261fabb4587700813ecb/thumb/1000)
- Thoughts.
    - Small numbers should be placed on the vertex with the smallest possible order of magnitude.
    - Small numbers should be placed near small numbers as much as possible.
    - If only we could prove it.
        - It's a tree, so there are lots of dots with rank 1.
        - Putting the smallest number x at a point of rank 1, one side is x
        - There is no way to get 0 edges to be x.
        - So it is best to place it on a point of rank one.
    - Just sort and place them in order of smallest to largest.
- Official Explanation
    - You're telling a very different story.
    - Method of placing the larger pieces first to solidify them.
    - I think the result is the same as my method of placing the smaller numbers from the end, since I place them from the larger ones while keeping the collection of larger numbers connected.
    - In principle, [[creating no fly zones]].
    - On my part [[fill in the blanks (at the end of a task)]].
    - It says you can check all the edges and O(N^2) will get you there in time, but it's probably O(N) with depth-first search.
        - My method, which is to start from the point with rank 1, is a depth-first search in the order of return multiplication.

---
This page is auto-translated from [/nishio/m_solutions2019D](https://scrapbox.io/nishio/m_solutions2019D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.