---
title: "Interval DP"
---

Dynamic programming with the interval $[l, r)$ as the domain of definition
![image](https://gyazo.com/c26ccf2850d1bbdee5d71cea1c3bc249/thumb/1000)
- There are several patterns in how to ask for it (sometimes in combination).
- 1:  [[Section DP to be shortened]]
    - Find f(l, r) from f(l + 1, r) and f(l, r - 1)
- 2:  [[Section DP to be divided into]]
    - Find f(l, r) from f(l, i) and f(i, r) (l < i < r)
    - O(N^3).
        - When you can't make it in time
        - Speed up range summation with phenic trees, etc.
- 3: Number of times to remove columns that satisfy the condition from the column
    - Figure from [PAST5L
        - We can remove a sequence of three elements that satisfy the condition
        - I want to maximize the number of pieces to remove.
        - I've done 1 and 2, and I'll do 3 in addition to that.
        - Pattern in which the remaining circles satisfy the condition after the section represented by the line is removed

- [[DP L]]
- [[DP N]]
- [[ARC108E]]
    - [[Deletion of a section]] 　 [[Section removal]]
    - [[PAST5L]]
    - [https://algo-logic.info/range-dp/](https://algo-logic.info/range-dp/)
    - [[palindrome]]


[https://www.hamayanhamayan.com/entry/2017/02/27/152226](https://www.hamayanhamayan.com/entry/2017/02/27/152226)

[https://www.hamayanhamayan.com/entry/2017/03/20/234711](https://www.hamayanhamayan.com/entry/2017/03/20/234711)



---
This page is auto-translated from [/nishio/区間DP](https://scrapbox.io/nishio/区間DP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.