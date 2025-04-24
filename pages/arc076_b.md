---
title: "arc076_b"
---

[https://atcoder.jp/contests/abc065/tasks/arc076_b](https://atcoder.jp/contests/abc065/tasks/arc076_b)
Thoughts.
    - The problem is to find the [[minimum area tree]], but if you do it naively, the side is 10^10, so it's no good.
- Focus on the vertex with the smallest x
        - [[fill in the blanks (at the end of a task)]]
    - This apex must be connected to any other than itself.
    - Connect to the point where x is next smallest, or connect to the point where y is closest.
    - It would be nice if the closest point of y could be found fast
        - Hmmm... I guess I'll bisect the [[segment tree]].
        - But you want to find them on the condition that "x is above a certain level."
    - Sort by y and put it in the [[bidirectional list]], and then just remove that x after you've tried it from the one with the smallest x.
        - Bidirectional lists are O(1) for deletion and O(1) for looking at the previous and next values.
            - [[Lists that only delete]] I thought I had thought of that before, but it was [[Zerofill's Linked List]].
        - Unlike this time, we want to access the i-th element with O(1)
        - Linked lists tend to think that the i-th access is slow, but that is the case when accessing the i-th access after adding and deleting, and when only deleting, accessing with i at the time of addition is O(1)
    - This will result in pre-processing O(NlogN) and main processing O(N)
- Official Explanation
        - [[Just look next door.]]
        - I use this in my solution where I'm only looking at "sorted by x and next" or "sorted by y and before/after".
    - Each point cannot be connected except back and forth in x-order and back and forth in y-order
        - → Reduce the number of edges to the order of N
        - →Minimum overall tree size
    - consideration
        - Should we consider whether we can reduce the number of edges in a minimum global tree problem when the edges do not make it in N^2 orders of magnitude?
            - [[Edge reduction → minimum global tree]]

---
This page is auto-translated from [/nishio/arc076_b](https://scrapbox.io/nishio/arc076_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.