---
title: "ABC134E"
---

[E - Sequence Decomposing](https://atcoder.jp/contests/abc134/tasks/abc134_e)
![image](https://gyazo.com/3f50fa55b41f2b055b35ff78691f2614/thumb/1000)

- Thoughts.
    - Focusing on groups of the same color results in a monotonically increasing sequence
    - Consider whether it is OK to use the greedy method, which is to start from the top and paint in the same color if there is a monotonous increase.
    - Suppose that some best solution, the value x, is monotonically increasing but has not been selected.
        - When a column ends before x or has a value y greater than x beyond x, x can be added without increasing the cost.
        - when this is not the case
            - Selecting x instead of y increases the number of columns starting with y by one, but decreases the number of columns starting with x by one, so there is no loss
                - Except if x is in a different column starting further forward.
    - Therefore, the following greed method is acceptable
        - Starting from the top, if it does not fit in any already existing monotonically increasing column, add a new monotonically increasing column.
        - PS: Omission of discussion on how to insert if you want to enter.
- Official Explanation
    - O(Nlog N) as matching the longest broadly monotonically decreasing sequence
    - LIS ([[LAM]]) problem attributed to the
        - [[Dilworth's theorem]]
- self-implementation
    - I noticed that you are not free to put in a monotonically increasing column when it could go into more than one of the already existing monotonically increasing columns.
        - 2,1,4,5,3 and the 5 must be placed in the column containing the 4
        - In other words, this, you have to find the smallest and largest value smaller than the number you put in.
        - Linear search is going to TLE in the worst case scenario.
        - The target is not static, so it cannot be sorted and dichotomized.
        - Binary search with phenic tree... the range of values is 10^9.
        - If we follow this policy, we would have to do [[coordinate compression]] → [[Fennic tree]] → [[dichotomous search]].
        - The amount of calculation is on the same order of magnitude as in the official explanation because of this preprocessing and the fact that a binary search is required in the main processing.
- Official Explanation
    - I'm looking at it from the back, as opposed to me.
        - Choosing the smallest one that meets the constraints is the flip side of my "smaller than the number you put in and the largest value" method.
    - The method of using a phenic tree is one of the solution methods of [LAM
    - I see, so "update the largest value that does not exceed x to x" keeps it sorted?
        - [[Updated and dichotomously searchable array]]



---
This page is auto-translated from [/nishio/ABC134E](https://scrapbox.io/nishio/ABC134E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.