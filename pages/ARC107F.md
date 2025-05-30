---
title: "ARC107F"
---

![image](https://gyazo.com/6e9ee2b88a1436d182987795574d233d/thumb/1000)

[F - Sum of Abs](https://atcoder.jp/contests/arc107/tasks/arc107_f)
![image](https://gyazo.com/4357c3c678c3b421398f123b3af31067/thumb/1000)
- Thoughts.
    - Known to be minimum cut entanglement
    - Delete vertices and divide into connected components
    - The absolute value of the sum of the B's of the connected components is the score.
    - Hmmm, I have no idea how to describe the connected component.
- [https://maspypy.com/atcoder-参加感想-2020-10-31arc107](https://maspypy.com/atcoder-参加感想-2020-10-31arc107)
    - I see. Okay.
    - Let's go to bed and consider it without looking at it tomorrow.
        - [[Absolute value is the maximum of positive and negative]]
    - $\left|\sum x_i\right| = \max\left(\sum x_i, \sum -x_i\right)$
        - This replaces the absolute value with a maximization problem.
    - (The one where the score is maximized by deleting vertices, and the other where the score calculation itself is maximized, so we'll consider them separately once, i.e., the graph is given and not edited.
    - At this time, it is a two-color paint job and a cut, since there are "two choices: plus or minus".
    - Must be the same among the consolidated components.
        - This can be converted to "if two vertices u,v are adjacent, then the colors of the two vertices must be the same".
            - [[Identical within a connected component = identical at adjacent vertices]]
        - This can be expressed by subtracting the INF edges from each other
    - We want to maximize the score. So we'll use the loss compared to the maximum score as the edge weight and make the minimum cut.
        - If written honestly, it has negative edges (see above).
        - Adding a sufficiently large number N (here 10) to all edges is shown below
            - The minimum cut is 19, and 2N-19 is the value you are looking for
        - ![image](https://gyazo.com/ca0017a873fa8ec8ad5c0a990e852096/thumb/1000)
        - ![image](https://gyazo.com/989ed2c781670342f21534d359643a8c/thumb/1000)

- Okay, so now we've calculated the score when the vertex is fixed.
- Next time a vertex is removed.
    - There are two choices: to delete a vertex or not to delete a vertex, and to delete a vertex, positive or negative.
    - This is what happens when you stick them together naively.
        - ![image](https://gyazo.com/c4369c6922fc0ef20ece52dcfad65821/thumb/1000)
        - But this won't work.
        - If the right side of S has zero cost, then cutting there would be the minimum.
            - Do we put 10 on here as well?
        - The vertex of 3 is erased, but the constraint on the infinity edge is still alive (you missed it in the diagram).
        - Only when it is "not erased" and "negative" should it be "infinite penalty if the neighbor is not negative".
- First, dig deeper into the "combination of two choices".
    - There are two choices this time, "turn off or not turn off" and "positive or negative," but it doesn't matter whether it's positive or negative when you turn it off.
    - Hmmm, but that would require wording like "no penalty for being painted negative when being erased"...
- Official Explanation
    - I see, so you don't have to deal with the painting of each of the two vertices and the two choices.
        - [[3 or more options with minimum cuts]]
    - ![image](https://gyazo.com/3d2a89d040886e82cbf3f92b2903ae3d/thumb/1000)
    - Don't try to map each of the two options to a vertex fill (because it's hard to do logical products and such).
    - Instead, place them in four different ways of multiplication.
    - TS can be eliminated by subtracting an infinity edge to BA.
    - Of the remaining three, A is T only when TT, B is S only when SS
    - The infinity edge is a constraint that "the tip must not be T when the root is S".
    - This expresses "when one vertex is positive, its neighbor must not be negative" (positive and negative are interchangeable, but not relevant here).
    - So it is decided to assign SS and TT to positive and negative (whichever is the better of the two).
    - ![image](https://gyazo.com/1e35dad9482f692232a562bb5f85ea26/thumb/1000)
        - Minimum cut so -3 that 3 is obtained when 3 is positive, the direction of getting better is small.
        - I don't think it's confusing to match the directions without first worrying about the edges being negative.
        - Then offset appropriately to eliminate negative edges
    - [[https://gyazo.com/1e35dad9482f692232a562bb5f](https://gyazo.com/1e35dad9482f692232a562bb5f)
    - ![image](https://gyazo.com/039cd4cd0142e78ff0cf8da6af4b884f/thumb/1000)
        - Each side increased by 10
    - minimum cut
        - ![image](https://gyazo.com/6e9ee2b88a1436d182987795574d233d/thumb/1000)
        - This means that the choice to eliminate 3 - 4 to 4
        - 10 x 2-16 equals 4.

---
This page is auto-translated from [/nishio/ARC107F](https://scrapbox.io/nishio/ARC107F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.