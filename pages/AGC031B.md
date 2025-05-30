---
title: "AGC031B"
---

![image](https://gyazo.com/1b9bf271902f33d4edff465f40136e47/thumb/1000)
[https://atcoder.jp/contests/agc031/tasks/agc031_b](https://atcoder.jp/contests/agc031/tasks/agc031_b)
- Thoughts.
    - I misunderstood the problem condition (I thought it was two colors, black and white), so I had to start over (moved to the end of the page).
        - [[Counting up the results of an operation]]
            - [[Counting up the results of an operation → What are the conditions under which the results of an operation are identical?]]
        - On the operation of overlapping sections
            - If the colors are different, it is impossible because the previous operation would make it inoperable.
                    - [[Uncombinable operations]]
            - The same color is the same as the manipulation of the combined section.
            - Therefore, the section of the operation can be assumed to be non-overlapping
        - For a continuous section of the same color.
            - No matter which endpoint is chosen, the result is the same.
    - First, prepare a row C' by collapsing consecutive same-colored squares into one square.
        - Focusing on the top, the number of cases in the remaining parts for the same color c=C'0 occurrences $i \in X(c)$ are added together
        - $f(0) = \sum_{i\in X(C'_0)} f(i+1)$
        - generally
            - $f(i) =  \sum f(j + 1) [j \in X(C'_i)][i < j]  $
        - The object of addition at each step is O(1) if and only if?
            - Looks bad when the colors alternate.
            - You can have a cumulative sum for each color.
        - Since it seems bad to pay O(N) for the calculation of X, if it is calculated collectively at the time of making C', O(N) can be calculated in total.


-----
- What I thought (misunderstanding the problem conditions)
    - Think black and white, block by block.
        - PS: You misunderstood the problem condition here.
    - If both ends are the same block, it will not change.
    - Where you take the edge in the block has no bearing on the outcome.
        - The number of stones in the block has no bearing on the outcome.
    - It doesn't matter what color the first block is or what color the result is.
    - Therefore, the result is determined from the number of blocks alone.
    - 1 street when 1 or 2
    - 2 ways when 3 pieces
    - When there are four, there are two options, both of which come down to when there are two.
        - DP-ish
        - f(4)=2f(2)+1
    - When 5
        - 3 ways to pinch 1 piece, 1 way to pinch 3 pieces
        - The two ways of sandwiching one will merge later, so the DP's gradual equation is suspect.
            - 10101 becomes 11101 and 10111, both of which can then become 11111
        - I'd rather use "When you decide to align to 1, there are 2 blocks of 0's that are not edges, so 2^2".
        - I'll do this on the side of aligning this to zero.
            - One street that does not change is common, so subtract one.
    - summary
        - Let N be the number of blocks.
        - 2^floor(N/2)+2^ceil(N/2)-1
- Official Explanation
    - DP with foolish O(N^2) and O(N) with ingenuity.
    - It's a little hard to understand what you mean.
    - Implement and test
        - Oh, I thought it was two colors, not black and white! problem condition misunderstanding
    - Official explanations are difficult to understand.
    - [https://drken1215.hatenablog.com/entry/2019/03/17/130800](https://drken1215.hatenablog.com/entry/2019/03/17/130800)
        - [[DP of separation position]]
            - [[dynamic programming]]
    - I agree with the explanation that there are only two ways to do it: either you don't pinch it, or you pinch it with the right end.

[[AGC031]]

---
This page is auto-translated from [/nishio/AGC031B](https://scrapbox.io/nishio/AGC031B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.