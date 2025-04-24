---
title: "abc057_d"
---

[D - Maximum Average Sets](https://atcoder.jp/contests/abc057/tasks/abc057_d)
![image](https://gyazo.com/9ee13215fbf4593c34a2ae8317907ae2/thumb/1000)

[https://atcoder.jp/contests/abc057/tasks/abc057_d](https://atcoder.jp/contests/abc057/tasks/abc057_d)

- Thoughts.
        - [[Mean Maximization]]
        - I wonder if we can transform the expression similar to [[Maximize the sum ratio]].
    - Maximize the mean is [[Maximize the sum ratio]] and is a special case where the denominators are all 1
        - You can transform the formula, sort it, greedy from larger, bisection search, and you're good to go.
        - Since the denominators are all the same value, they disappear in the equation transformation and end up sorted by value from largest to smallest
    - We are also told to seek the maximum number of pieces
        - When choosing from the larger number, the last form is to choose k from the same n. Here n to k is the number of combinations to choose from.
- Official Explanation
    - omission from consideration
        - There is a range in the number of pieces to choose from.
        - Generally speaking, if you choose from the larger number, increasing the number of pieces to choose from will only lower the average.
            - The exception is when the average value and the increasing value are the same, i.e., when there are many things with the highest value and you only select the ones with the highest value.
            - Counting at this time requires one more step.

---
This page is auto-translated from [/nishio/abc057_d](https://scrapbox.io/nishio/abc057_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.