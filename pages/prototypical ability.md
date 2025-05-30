---
title: "prototypical ability"
---

[Strengths and "Typical Strengths" of competitive programming - chokudai's blog](http://chokudai.hatenablog.com/entry/2018/04/23/165232)
- [It's more like what we used to call "Power of Attribution.

Ability to enumerate the components to derive a solution in situations where the problem is only partially given.

I guess I'd better think for myself first and then see the difference.
[[AGC022C]]
- Thoughts.
    - Multiple operations on the same k are useless.
    - Unless the maximum value of k, M, is very small, it is impossible to search the whole area.
    - The order of operations cannot be ignored because it affects the result.
        - Is it determined by some greed law or other?
    - For example, divide 9 by 3 and 5.
        - 0 if divided by 3 first
        - Divide by 5 and stop, 4
        - Divide by 5, then divide by 3, and you get 1.
        - 9 if not broken
        - If it is bare, the possibility increases by a factor of two.
    - OK assuming the larger one is done first?
    - On the other hand, when can't you do it?
        - Cannot be greater than the original number.
        - Can't be more than half the original number.
    - Effect of the cost being 2^k
        - Cheaper to do all operations under x than once with x+1
        - Consistent with the search for the lowest cost order adding options from the smallest to the largest.
        - [[Working backwards from the goal]]
        - Think before dividing by 2
            - When the goal is x<2, one step forward is 2n+x
            - Don't consider anything greater than half of the start, because it's unattainable.
        - Think before dividing by 3 in the next step.
            - Only those less than 3 should be considered (no value greater than 3 can appear as too much divided by 3).
        - Once the starting number is painted, there is no need to think about that number in the future.
        - OK when all starts are painted.
        - Now we can determine whether or not there is an optimal solution without regard to computational complexity.
    - Constraints on the problem, N is 50, M is also 50, rather small
        - You can put 50 Eratosthenesian tables of 50 on each of the 50 numbers.
        - At worst, it won't be 50^3, so you can afford it.
    - Mark the table" is expressed by writing the cost.
        - There is a shortest path problem-ish.
        - The search starts with the lowest cost and ends when the distance to the goal is determined.
- Confirmation of official explanation
    - My solution doesn't work.
        - There are cases where the paths to reach the goal are different: if the goal is reached by 100 and 011, the simple or is 111, but it is possible to reach the goal by 110 in addition to the shortest 011, in which case the overall shortest path is 110.
        - [[Doing it twice doesn't make sense.]]
        - [[The optimal order of operation is first]]
        - Because it doesn't make sense to do a small value operation and then do a large value operation.
        - [[Cost is 2^k -> smallest in lexicographic order]]
    - My solution was to see if I could solve it using 1-x.
        - I expected to find the shortest solution at this time as well, but I was wrong.
        - It would be useful to slightly modify the "can it be solved by 1 - x" component to "can it be solved by the set S".
        - When it can be solved for 1-x and cannot be solved for 1-x-1, x is essential."
                - [[When 1 to x is sufficient and 1 to x-1 is not, x is required]]
        - The official explanation for this component is BFS or DFS. My method is equivalent to BFS.
- chokudai commentary
    - The image is divided into much finer pieces.
    - The problem statement itself is also divided and abstracted.
    - Recognizing a problem as "a combination of components smaller than the problem" allows us to see a problem as "a combination of known components" even if we are seeing it for the first time
    - When I thought of [[problem transformation]], I recognized the whole problem as one component.
    - Rather, it is important to first divide and recognize the problem
        - [[problem partitioning]]

    - [[Compression of state information]]
    - The order is determined in some way, so just tell us how many have been visited.

---
This page is auto-translated from [/nishio/典型力](https://scrapbox.io/nishio/典型力) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.