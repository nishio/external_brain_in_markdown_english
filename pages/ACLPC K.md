---
title: "ACLPC K"
---

from [[AtCoder Library Practice Contest]]
ACLPC_K
[K - Range Affine Range Sum](https://atcoder.jp/contests/practice2/tasks/practice2_k)
- ![image](https://gyazo.com/5b8f41c3ba45a6f2bcaeb91a7353f862/thumb/1000)
- Delayed Segment Trees] since it is a range update range contraction.
- First, I had the action in tuples and TLE
- AC by shifting 32 bits and bundling them into a single integer.
- I bugged it with things like shift operator precedence order, not taking C modulus, outflanking 32 bits, and so on.

---
This page is auto-translated from [/nishio/ACLPC K](https://scrapbox.io/nishio/ACLPC K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.