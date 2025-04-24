---
title: "ABC147D"
---

[D - Xor Sum 4](https://atcoder.jp/contests/abc147/tasks/abc147_d)
- ![image](https://gyazo.com/937c69af3cbbbb3b69f4e85db5d14453/thumb/1000)
- Thoughts.
    - Do not calculate in square orders.
    - Exactly half of the entire queue [[Half of the queue]].
    - I wonder if the XOR and the order of the sums could be interchanged...
    - It would be difficult to add all the digits, but I guess it could be done bit by bit.
    - OK, the following holds for the 0/1 column
    - $\sum_i^N x_i = K \iff \sum_i^N (1 \oplus x_i) = N - K$  [[XOR and Sum Exchange]]
    - In other words, you can count the number of 1's for each digit of all the numbers in advance, and find the sum by inverting the above formula only where the 1 in Ai stands, which is fast enough since the number of digits is 60.
    - Since what we have obtained here is the whole matrix, we can halve it to get the answer
- Official Explanation
    - The above is sufficient, but the official explanation does a similar conversion further
    - $\sum_j \sum_i (x_i \oplus x_j) = \sum_j ([x_j = 0]  K + [x_j = 1] (N - K)) =  (N - K) K + K (N - K)$
    - Since the value we want is half of this $K (N - K)$.

---
This page is auto-translated from [/nishio/ABC147D](https://scrapbox.io/nishio/ABC147D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.