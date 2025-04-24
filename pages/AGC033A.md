---
title: "AGC033A"
---

[A - Darker and Darker](https://atcoder.jp/contests/agc033/tasks/agc033_a)
- ![image](https://gyazo.com/7a7d1b269831ffa3937f83c49b7391de/thumb/1000)

- Thoughts.
    - At best 10^6 vertices, at worst 10^3 times processing.
    - If you check every vertex every time, you won't make it in 10^9, but you don't do that.
    - If we do a width-first search, the process will be completed in 10^6 orders of magnitude, which is OK.
    - [[Official Explanation OK]]
    - I was unconsciously rewriting the problem.
    - For all black squares, if there is a white square adjacent to the black square, it is black" is the same as "For all black squares, if there is a white square adjacent to the black square, it is black
            - [[The white square adjacent to the black square is turned to black]]
        - Sure would have bothered me if I hadn't noticed this rephrasing.
        - In the latter, once a black square has been dealt with, there will be no more white squares around it [[Never have to deal with it again.]], and this is the principle of reduced order.


---
This page is auto-translated from [/nishio/AGC033A](https://scrapbox.io/nishio/AGC033A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.