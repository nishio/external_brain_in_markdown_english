---
title: "ABC019C"
---

[C - Takahashi-kun and the Magic Box](https://atcoder.jp/contests/abc019/tasks/abc019_3)
![image](https://gyazo.com/1aaceef3c8e29db0b95df8a27619e4ca/thumb/1000)
- Thoughts.
    - Since x and 2x are identical, we can just divide by as much as we can divide by 2.
        - representative source of equivalence class
    - The number of times to break it is about 30 times, so there is plenty of time to spare.
- Official Explanation
    - Oh, I see, I didn't explain enough about the determination of "whether or not the number has already been obtained".
    - So the number of numbers is about 10^5, but the range of values is 10^9, so you don't want to have an array with or without occurrences.
    - I didn't explain it, but I would put it in a Python set without thinking too much about it. This is a hash table, so O(1)

[[ABC019]]

---
This page is auto-translated from [/nishio/ABC019C](https://scrapbox.io/nishio/ABC019C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.