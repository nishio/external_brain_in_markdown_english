---
title: "ABC016D"
---

[D - One Sword](https://atcoder.jp/contests/abc016/tasks/abc016_4)
![image](https://gyazo.com/ef23ddd076030dd0b8a2ceedbd0ff39d/thumb/1000)
- Thoughts.
    - This is a pain in the ass.
    - Determine the intersection of line segments and sort the intersection points
    - Alternate because we know the chop starts from the outside.
    - Connect odd-numbered intersections with even-numbered intersections. Since we are dealing only graphically, it is sufficient to connect the two ends of the cut edges, but it is necessary to avoid twisting the edges.
        - We can't use the inner product to determine that, so we'll do a line segment crossing determination.
    - Once you have the edge set, just count the number of connected components.
        - I wonder what [[Line segment intersection judgment]] would have done.
        - I see, just project it onto the normal vector and see if the signs are reversed.
    - I've got an article up to the point where I'm looking for intersections, so I'll put it in my library later.
        - [https://qiita.com/kaityo256/items/988bf94bf7b674b8bfdc](https://qiita.com/kaityo256/items/988bf94bf7b674b8bfdc)
- Official Explanation
    - Oh, I only counted the number of cut edges.
    - Okay, you say "polygonal" so there are no holes.
    - I thought too hard.

[[ABC016]]

---
This page is auto-translated from [/nishio/ABC016D](https://scrapbox.io/nishio/ABC016D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.