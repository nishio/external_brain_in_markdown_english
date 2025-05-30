---
title: "ABC174E"
---

![image](https://gyazo.com/d918641f069655a20c15816f05aa0133/thumb/1000)

from [[ABC174]]
ABC174E
![image](https://gyazo.com/1a24dd1ea8f7b2400d189a120215cb44/thumb/1000)

[E - Logs](https://atcoder.jp/contests/abc174/tasks/abc174_e)
    - [[dichotomous search]] I realized it was a dichotomous search, and I implemented it, but I used up all my time thinking that the subtle discrepancy must not be a good reason to use a simple dichotomous search.
- When I compared my code to the strong man's code, I found two bugs in my code
    - How could I have known?
- Thoughts during the contest
    - ![image](https://gyazo.com/4eb43b6ef20a3f75aa8708896d8b7c2d/thumb/1000)
    - First consider the case of one
            - [[Minimize Maximum]] will result in an even split.
    - For each log, find the length of the log if it is divided into k logs, so that the sum of k is k. DP...
        - This is impossible.
        - Because there are 10^9 in the k direction.
    - Then let's turn the tables and focus on the length of the chop.
        - Nice that you came up with this idea on your own.
            - Ideas similar to [Exchange of value range and definition range
        - Reverses the composition with the number of bottles as the defining domain and the length as the value domain
    - The length to be engraved as the definition range and the number of pieces to be engraved as the value range.
        - The shorter the length, the greater the number of pieces.
        - →Binary search can be used to find the desired value
    - dichotomous search
        - left = 1
        - right = min(AS)
        - s = sum(a // x - 1 for a in AS)
        - s >= K
    - right = min(AS)
        - error
        - K cuts may be made without cutting the shortest log
        - right = max(AS) is correct
            - In this case, the number of possible disconnections is zero.
    - left = 1
        - error
        - Chopping by length 1 may not lead to K times.
        - I set left = 0, but in retrospect, I was a little lukewarm in this area.
    - s = sum(a // x - 1 for a in AS)
        - error
        - I discovered by setting right = max(AS), but it is negative when x is greater than a
        - Easily patched with conditional branching.
            - sum(a // x - 1 if a >= x else 0 for a in AS)
            - error
            - I didn't realize it until the contest ended, but this is the biggest mistake I made.
            - ![image](https://gyazo.com/9b66f0994c8a6d7bc7e22ed4396fb528/thumb/1000)
            - You can take three 3's out of 10.
            - So at the longest 3, 10 is divided into 3, the number of disconnections is 2." Wrong.
                - It's at 3.3, rounded up to 4.
            - Cut three times at 10, twice at 9.
            - Given this, sum((a - 1) // x for a in AS) is correct
            - If I had drawn this diagram, I would have known...
    - s >= K
        - error
        - ![image](https://gyazo.com/d918641f069655a20c15816f05aa0133/thumb/1000)
        - The problem condition to return the rounded up value requires that the right side be returned when there is no matching value
        - So when it comes time to match, it needs to go in on the right side.
        - The code to put in left when s is greater than or equal to K is wrong, s > K is correct.
- summary
    - I had all four components of the binary search wrong, two of which I was able to correct on my own during the contest, but with two remaining, I got lost, thinking, "This must not be solved by a simple binary search.
        - [Binary Search Checklist

---
This page is auto-translated from [/nishio/ABC174E](https://scrapbox.io/nishio/ABC174E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.