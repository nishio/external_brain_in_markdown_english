---
title: "ABC172F"
---

[F - Unfair Nim](https://atcoder.jp/contests/abc172/tasks/abc172_f)
- ![image](https://gyazo.com/d09c9c7d427d3fd5824bf5f4beb257b1/thumb/1000)
- Thoughts.
    - competitive game
    - I'm not sure about the weighting between consideration and implementation, but let's consider it.
        - When there is only one mountain, you win if you get them all.
        - when two mountains are rising
            - If it's 1,1, you lose.
            - If x,x, no matter how you take it, it will return to the x,x form, so you lose.
            - If not, then you win in the form of x,x
        - when there are three mountains
            - If a,b,b, you win by taking all a's.
                - So is a,a,a.
            - When a,b,c
                - If you get some number somewhere for taking it, you lose.
                - Three numbers in a row, you lose.
                - If all but c are contiguous, move c to be contiguous and win.
                - If there is a gap before b, count 2. If the total number of gaps is odd, win?
                    - No, we can jump the order and attack to fill in the gaps.
- Official Explanation
    - I'm assuming "if the XOR of each number is 0, the latter wins" is known about Nim.

- [[unAC]]

---
This page is auto-translated from [/nishio/ABC172F](https://scrapbox.io/nishio/ABC172F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.