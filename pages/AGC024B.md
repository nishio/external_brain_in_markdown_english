---
title: "AGC024B"
---

[B - Backfront](https://atcoder.jp/contests/agc024/tasks/agc024_b)
![image](https://gyazo.com/c45a7bf6e5e9f8696fb1c193eb80eaa5/thumb/1000)
- Thoughts.
    - N times is enough
    - Never move the same thing twice.
        - If you only do it the second time, the result is the same.
            - [[Doing it twice doesn't make sense.]]
    - So, for a given one, the problem is divided into "move it to the beginning", "move it to the end", and "don't move it".
    - The ones that were not moved need to be in ascending order.
    - Find the smallest sum of a and b such that the remainder is in ascending order when a from the smallest number is eliminated and b from the largest number is eliminated.
    - Order of squares in a naive search.
    - Conversely, find the longest "such columns that are in ascending order
    - Create "number -> position" in linear order.
    - Count while the number is increasing, reset when it decreases, and find the location with the largest count.
        - This is a linear order
- Official Explanation
    - OK

- [[problem partitioning]]
    - [[Ascending sorting of number sequence]]
    - [[Minimize the number of operations]]

[[AGC024]]

---
This page is auto-translated from [/nishio/AGC024B](https://scrapbox.io/nishio/AGC024B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.