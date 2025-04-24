---
title: "codefestival_2016_qualB_c"
---

[https://atcoder.jp/contests/code-festival-2016-qualb/tasks/codefestival_2016_qualB_c](https://atcoder.jp/contests/code-festival-2016-qualb/tasks/codefestival_2016_qualB_c)

- Thoughts.
    - The problem of creating a [[minimum area tree]] with a rectangle of points.
    - It doesn't seem to make the whole area tree in the yang because there are 10^10 points.
        - [[fill in the blanks (at the end of a task)]]
        - The corner house can only be connected in two ways, so it should be connected in the smaller way.
        - We do not lose generality if we consider this to be vertical.
        - There are only two ways to connect again.
            - If this is below, the same argument is repeated recurrently
        - If it is horizontal, then moving the path up does not change the cost.
        - hmm
        - Consider the [Kruskal method
        - Select the shortest vertex and connect it.
        - In this problem condition, all the roads connecting i and i+1 have the same cost
        - Select one of the smallest vertical and horizontal costs
            - If you condense it all, you get a slightly smaller rectangle.
                - ![image](https://gyazo.com/2916eb83214b0fd8a81a9816918f646a/thumb/1000)
            - Repeat until you reach a point.
            - That means using all of them.
            - Sort p and q respectively $\sum_i p_i (H-i)$.
- Official Explanation
    - I WA'd at the last step, I should have sorted them together and calculated them in order, because when I connected the verticals, the number of horizontal ones decreases.
        - [[grid graph]]

---
This page is auto-translated from [/nishio/codefestival_2016_qualB_c](https://scrapbox.io/nishio/codefestival_2016_qualB_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.