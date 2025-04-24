---
title: "keyence2020 d"
---

from  [[Typical ideas for coming up with solutions in competitive programming]]
keyence2020_d
[https://atcoder.jp/contests/keyence2020/tasks/keyence2020_d](https://atcoder.jp/contests/keyence2020/tasks/keyence2020_d)
- Thoughts.
    - N=18
    - Since the operation can be repeated infinitely, first consider the "set reachable by repeating the operation"?
        - Is it subtle because it also requires a minimum number of times required?
    - Can repeat compatibility in any order
    - Flip over if it's an odd number away from the original position.
    - 2^18 is less than 10^6, I'd say that's within the computable range of multiplying by 18.
        - No, it's a permutation, so 18!
    - If the constraints were not met when the first and second cards were set, they will not be met thereafter.
        - But you can't search while pruning branches with this, because it would be a full search in cases where everything has the same value.
        - This kind of case could be quickly obtained by finding the minimum value.
- Official Explanation
    - [[bit DP]]
    - I'm not sure of the specifics.
- [https://www.hamayanhamayan.com/entry/2020/01/18/233933](https://www.hamayanhamayan.com/entry/2020/01/18/233933)
    - > Minimum value of the operation when the already aligned set is msk and the last value is lst
    - The set of used values is 2^N, so express this in bits
    - I'm not sure if that is enough to keep the "monotonic increase" and add to it, so I'll hold the last card as well.
    - O(N 2^N)

![image](https://gyazo.com/227ef044f17cd3088465d5c3121bc561/thumb/1000)
- The order of operation is irrelevant.

---
This page is auto-translated from [/nishio/keyence2020 d](https://scrapbox.io/nishio/keyence2020 d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.